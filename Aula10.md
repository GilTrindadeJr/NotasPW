# Aula 10 — PWA, Testes Automatizados, Build e Implantação

**Professor da disciplina:** Me. Deivison S. Takatu

> Material temático de revisão elaborado com base nos projetos desenvolvidos durante o semestre. A numeração possui finalidade organizacional, não correspondendo a uma aula oficial ou a uma data confirmada.

## Resumo

O conteúdo aborda os processos necessários para preparar uma aplicação web para publicação, distribuição e manutenção. Os conceitos são associados ao projeto Ecoa, possibilitando a compreensão dos fundamentos teóricos por meio de sua aplicação prática.

## Objetivos de aprendizagem

- Assimilar os principais conceitos relacionados a PWA, testes, build e implantação de aplicações.
- Reconhecer a utilização desses recursos no código-fonte e na organização do projeto.
- Associar os conhecimentos adquiridos ao desenvolvimento e à manutenção de sistemas web.

## Conteúdo principal

- Configuração do Web App Manifest e instalação da aplicação.
- Funcionamento do Service Worker, seu ciclo de vida e gerenciamento de cache.
- Possibilidades e limitações de funcionamento sem conexão com a internet.
- Utilização do Node.js e execução de scripts npm.
- Processo de build e geração do diretório dist.
- Implementação de testes automatizados.
- Hospedagem na Vercel e utilização de funções serverless.
- Controle de versão com Git, realização de commits e revisão de alterações.
- Distinção entre ambientes de desenvolvimento e produção.

## Aplicação prática no projeto

O Ecoa apresenta arquivos e diretórios relacionados à instalação, validação, preparação e publicação da aplicação, incluindo manifest.json, sw.js, build.cjs, validar.cjs, tests e vercel.json.

A documentação disponível no README apresenta os seguintes comandos:

- npm run dev: inicia o ambiente de desenvolvimento.
- npm test: executa os testes da aplicação.
- npm run build: prepara os arquivos destinados ao ambiente de produção.
- npm run preview: permite visualizar a versão gerada pelo build.

Algumas funcionalidades que dependem de serviços externos podem exigir conexão com a internet.

## Metodologia e recursos

Estudo do código-fonte, consulta à documentação técnica, avaliação da estrutura do repositório e realização de exercícios de implementação. As atividades apresentadas a seguir possuem caráter de revisão, não representando tarefas oficiais solicitadas pelo professor.

## Atividades de revisão

1. Executar os testes automatizados e realizar o build da aplicação.
2. Analisar o funcionamento do cache após o primeiro acesso.
3. Verificar o comportamento das funcionalidades sem conexão com a internet.
4. Examinar os arquivos gerados para produção e as configurações utilizadas na hospedagem.

## Referências

- [Repositório do projeto Ecoa](https://github.com/ZPoizon/Ecoa)
- [Documentação sobre Progressive Web Apps — MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)
- [Caderno de Programação Web](./README.md)

---

Material de revisão produzido a partir dos arquivos e da documentação dos projetos acadêmicos.

---

## Serviços geográficos e armazenamento de informações

| **Tecnologia** | **Implementação e finalidade** |
| --- | --- |
| Photon | Utilizado no arquivo enderecos.js para geocodificação direta e reversa por meio dos endpoints https://photon.komoot.io/api/ e /reverse |
| ViaCEP | Consulta de códigos postais no arquivo enderecos.js, utilizando /ws/{codigo}/json/ |
| Overpass API | Utilizada em pontos-osm.js para consultar informações do OpenStreetMap por região e categoria, através de overpass-api.de e overpass.private.coffee |
| Leaflet | Biblioteca responsável pela apresentação dos mapas, conforme documentado no README |
| OpenStreetMap | Fonte de informações geográficas, distinta da biblioteca Leaflet |
| Google Maps | Geração de links externos para rotas no arquivo pontos-osm.js |
| Supabase/PostgreSQL | Gerenciamento de informações compartilhadas por meio de pontos-compartilhados.js e supabase/schema.sql |
| localStorage | Armazenamento do planejamento pessoal e de suas associações com pontos no arquivo plano.js |
| pdf-lib | Geração e exportação de documentos PDF por meio do módulo plano-pdf.js |

O mecanismo de preenchimento automático de endereços utiliza uma técnica de debounce com intervalo de 350 milissegundos, iniciando as consultas após a digitação de pelo menos três caracteres.

As requisições anteriores podem ser canceladas utilizando AbortController. A interface também emprega atributos ARIA para auxiliar na acessibilidade e na navegação por teclado.

O módulo responsável pelos dados do OpenStreetMap realiza consultas utilizando bounding box, uma área geográfica delimitada por coordenadas. As informações recebidas são convertidas e combinadas com os pontos disponíveis localmente.

O funcionamento dessas integrações depende da disponibilidade dos serviços externos e da cobertura de informações na região pesquisada.

## Estrutura do banco de dados e segurança

O arquivo schema.sql estabelece as tabelas public.pontos e public.denuncias, ambas utilizando identificadores UUID como chaves primárias.

O campo denuncias.ponto_id funciona como uma chave estrangeira associada a pontos.id, utilizando a configuração ON DELETE CASCADE.

A estrutura também apresenta restrições CHECK destinadas à validação de categorias, status, coordenadas e informações textuais.

As extensões unaccent e pg_trgm são empregadas para auxiliar nas pesquisas textuais sem diferenciação de acentos e na utilização de índices GIN.

Além disso, existem índices parciais relacionados aos pontos aprovados, considerando informações como cidade, categoria e área geográfica.

### Controle de acesso com RLS

O código SQL habilita o Row Level Security (RLS) nas duas tabelas do banco de dados.

O perfil de visitante anônimo, identificado como anon, possui permissão SELECT na tabela pontos. Entretanto, a política de segurança limita a visualização aos registros que apresentam status aprovado.

A possibilidade de cadastrar novos pontos anonimamente foi removida. Embora a antiga política de INSERT permaneça definida, não existe uma autorização GRANT correspondente para permitir essa operação.

Os visitantes podem registrar denúncias de pontos aprovados, informando somente ponto_id e motivo. Não possuem autorização para realizar operações de atualização ou exclusão de registros.

Um trigger é responsável por incrementar a quantidade de denúncias registradas no banco de dados.

```sql
-- Exemplo da política de leitura utilizada no projeto
create policy "Visitante le apenas aprovados"
on public.pontos for select to anon
using(status='aprovado');
```

Os mecanismos RLS e GRANT trabalham em conjunto para estabelecer as permissões e as restrições de acesso às informações.

A chave pública utilizada pela aplicação não deve ser confundida com a chave secreta de serviço, que precisa permanecer protegida.

## Persistência do planejamento pessoal

O planejamento pessoal não é sincronizado automaticamente entre dispositivos por meio do Supabase.

O arquivo plano.js utiliza JSON.stringify para converter as informações em um formato adequado ao armazenamento local e JSON.parse para recuperar os dados posteriormente.

A aplicação também disponibiliza funcionalidades de importação e exportação das informações, possibilitando a criação e a recuperação de cópias de segurança.

**Fontes:** Arquivos enderecos.js, pontos-osm.js, schema.sql e plano.js do projeto Ecoa.
