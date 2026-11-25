# Aula 09 — Ecoa — Desenvolvimento de Interfaces, Armazenamento e Integrações

**Professor da disciplina:** Me. Deivison S. Takatu

> Material temático de revisão elaborado com base nos projetos desenvolvidos durante o semestre. A numeração possui finalidade organizacional, não correspondendo a uma aula oficial ou a uma data confirmada.

## Resumo

O Ecoa aplica os conhecimentos adquiridos na disciplina de Programação Web em uma plataforma educativa voltada aos 17 Objetivos de Desenvolvimento Sustentável (ODS).

A aplicação auxilia os usuários na identificação de ações sustentáveis de acordo com sua disponibilidade de tempo, seus recursos financeiros e sua realidade. Trata-se de uma iniciativa independente, sem vínculo oficial com a Organização das Nações Unidas (ONU).

## Objetivos de aprendizagem

- Associar o levantamento de requisitos, a experiência do usuário e a estruturação do código.
- Compreender as diferenças entre armazenamento local e compartilhamento de informações.
- Implementar integrações com APIs e entender os mecanismos de controle de acesso aos dados.

## Interface e estrutura da aplicação

- Identificação do problema, definição dos requisitos e implementação de filtros relacionados ao tempo e ao orçamento.
- Organização dos arquivos HTML, CSS e JavaScript conforme suas respectivas responsabilidades.
- Desenvolvimento de interfaces responsivas, recursos de acessibilidade, navegação por teclado e retorno visual das interações.
- Divisão da aplicação nas seções Agir, Aprender, Na cidade e Meu espaço, disponibilizando ações, materiais educativos, questionários e planejamento pessoal.
- Diferenciação entre conteúdos oficiais, recomendações educativas e cálculos estimados.

## Armazenamento de dados e integração com serviços

| **Tecnologia** | **Finalidade na aplicação** |
| --- | --- |
| localStorage e JSON | Armazenamento do planejamento pessoal, das preferências e de cópias de segurança no navegador |
| Leaflet e OpenStreetMap | Apresentação de mapas e localização de estabelecimentos e espaços |
| Overpass, Photon e ViaCEP | Consulta de informações geográficas, endereços e códigos postais |
| Supabase e PostgreSQL | Gerenciamento de dados compartilhados e controle de acesso utilizando RLS |
| pdf-lib | Geração e exportação do planejamento pessoal em formato PDF |

O armazenamento realizado no navegador não permite a sincronização automática das informações entre diferentes dispositivos.

As funcionalidades que utilizam serviços externos dependem da conexão com a internet e da disponibilidade das respectivas APIs.

A chave pública do Supabase pode ser utilizada no lado do cliente. Entretanto, informações secretas devem permanecer protegidas, e as políticas de segurança do banco de dados precisam limitar adequadamente o acesso aos registros.

## Atividades de revisão

1. Utilizar os filtros disponíveis e adicionar uma ação ao planejamento pessoal.
2. Atualizar a página e verificar se as informações permanecem armazenadas.
3. Realizar a exportação de uma cópia de segurança e gerar o documento PDF.
4. Consultar um endereço e identificar os serviços responsáveis pelas informações geográficas.
5. Avaliar a adaptação da interface a diferentes telas, a navegação por teclado e as mensagens apresentadas ao usuário.
6. Analisar as políticas de acesso aos dados em um ambiente de testes, evitando a exposição de informações secretas.

As atividades propostas possuem finalidade de revisão, envolvendo análise de código-fonte, consulta à documentação e exercícios de implementação. Não correspondem a tarefas oficiais solicitadas pelo professor.

## Referências

- [Objetivos de Desenvolvimento Sustentável — ONU Brasil](https://brasil.un.org/pt-br/sdgs)
- [Documentação do Supabase — Row Level Security](https://supabase.com/docs/guides/database/postgres/row-level-security)
- [Aula 10 — PWA, testes, build e publicação](./Aula_10_Resumo.md)
- [Caderno de Programação Web](./README.md)

---

## Estrutura e responsabilidades dos arquivos do Ecoa

| **Arquivos presentes em public/** | **Finalidade** |
| --- | --- |
| index.html, app.js, estrutura.js | Estruturação da interface e organização geral do sistema |
| rotas.js | Gerenciamento da navegação por hash, histórico e abas |
| acoes.js, agir.js, agir.css | Organização do catálogo e pesquisa de ações sustentáveis |
| guias.js, aprender.js, quiz.js, quiz-ui.js | Disponibilização de materiais educativos e questionários |
| estimativa.js, estimativa-ui.js | Processamento e apresentação das estimativas de impacto |
| cidade.js, cidade-ui.js, cidade-busca.js | Consulta e apresentação de informações sobre locais |
| plano.js, progresso.js, desafio.js, rotina.js | Gerenciamento do planejamento e acompanhamento das atividades |
| design-system.css, acessibilidade.js, acessibilidade.css | Padronização visual e implementação de recursos de acessibilidade |

A aplicação não utiliza frameworks de interface. Seu desenvolvimento é baseado em JavaScript puro, com a organização dos arquivos conforme suas responsabilidades e a utilização de scripts próprios para o processo de build.

A função resolverRotaEcoa(hash), juntamente com os eventos hashchange e popstate, permite controlar a navegação utilizando fragmentos da URL, sem depender de ferramentas como React Router ou Vue Router.

O sistema de navegação também é responsável pelo gerenciamento do foco dos elementos durante a utilização do teclado e pela alternância entre abas.

## Regras de negócio e cálculo de estimativas

O arquivo estimativa.js realiza a validação dos valores informados antes de executar os cálculos, verificando entradas numéricas, intervalos permitidos e campos que exigem números inteiros.

Entre as fórmulas utilizadas na aplicação, destacam-se:

- Consumo de água em banhos: diferença entre a duração anterior e a nova duração, multiplicada pela vazão de 10 litros por minuto e pela quantidade de banhos.
- Consumo de energia elétrica: potência em watts, multiplicada pela quantidade de equipamentos, horas de utilização e número de dias, dividindo o resultado por 1.000 para obter o consumo em kWh.
- Quantidade de alimentos: conversão de gramas para quilogramas mediante divisão por 1.000.
- Quantidade de óleo: conversão de mililitros para litros mediante divisão por 1.000.

### Exemplo de estimativa de economia de água

Considerando uma redução de cinco minutos na duração de dez banhos e uma vazão constante de dez litros por minuto:

```text
Economia estimada = 5 × 10 × 10
Economia estimada = 500 litros
```

O resultado representa uma projeção baseada nos parâmetros estabelecidos, não uma medição efetiva do consumo de água.

A aplicação apresenta as fontes utilizadas e as limitações relacionadas aos cálculos, permitindo distinguir estimativas educativas de resultados reais.

**Fontes:** Arquivos rotas.js, estimativa.js e demais recursos presentes no diretório public/ do projeto Ecoa.