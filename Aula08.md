# Aula 08 — Vue, Vite e Angular — Arquitetura de Front-end

**Professor da disciplina:** Me. Deivison S. Takatu

> Registro temático de revisão. A numeração possui finalidade organizacional e não representa uma aula oficial ou data confirmada.

## Resumo

O conteúdo apresenta a organização de aplicações Vue e os conceitos de ferramentas modernas de front-end, estabelecendo comparações com React e Angular. Os projetos projeto-vue, projeto-template e projeto-angular são referências para essa revisão.

## Objetivos de aprendizagem

- Compreender os fundamentos de Vue e Vite.
- Identificar a organização de componentes e recursos de front-end.
- Comparar as características de React, Vue e Angular.
- Relacionar arquitetura, organização e manutenção de aplicações web.

## Conteúdo principal

- Single File Components (.vue).
- Composition API e reatividade.
- JavaScript e TypeScript.
- Vue Router e navegação declarativa.
- Pinia e gerenciamento de estado compartilhado.
- Element Plus e bibliotecas de interface.
- Axios e comunicação HTTP.
- SCSS e UnoCSS.
- Vite, pnpm, ESLint e Vitest.
- Componentes, páginas, layouts, rotas e serviços HTTP.
- Introdução à arquitetura de aplicações Angular.

As ferramentas citadas fazem parte do conteúdo de revisão. Sua utilização específica nos repositórios deve ser confirmada pelas dependências e pelos arquivos de configuração.

## Aplicação prática nos projetos

| Projeto | Descrição disponível |
| --- | --- |
| projeto-vue | Projeto Vue desenvolvido para atividade acadêmica, identificado como JavaScript |
| projeto-template | Projeto identificado como Vue e disponibilizado sob licença MIT |
| projeto-angular | Projeto Angular desenvolvido para atividade acadêmica, identificado como TypeScript |
| projeto-react | Aplicação React com cinco funcionalidades |

O projeto-template permite propor uma revisão da organização de interfaces baseadas em modelos. A identificação do template original, sua autoria e suas dependências deve ser realizada a partir do README, do arquivo de licença e do código. A licença MIT não comprova que se trate do template V3 Admin Vite citado no texto anterior.

## Organização de aplicações front-end

| Recurso | Finalidade |
| --- | --- |
| Componentes | Dividir a interface em partes reutilizáveis |
| Páginas e layouts | Organizar a estrutura visual da aplicação |
| Roteamento | Controlar a navegação entre páginas |
| Estado compartilhado | Disponibilizar informações a diferentes componentes |
| Serviços HTTP | Centralizar a comunicação com APIs |
| Ferramentas de build | Preparar os arquivos para distribuição |
| Testes e lint | Auxiliar na qualidade e manutenção do código |

Essas responsabilidades podem ser distribuídas em diferentes arquivos e diretórios, conforme a arquitetura adotada por cada projeto.

## Comparação entre React, Vue e Angular

| Característica | React | Vue | Angular |
| --- | --- | --- | --- |
| Interface | JSX | Templates e arquivos .vue | Templates HTML e componentes |
| Lógica | Hooks e componentes | Composition API ou Options API | Componentes e serviços |
| Linguagem | JavaScript ou TypeScript | JavaScript ou TypeScript | Principalmente TypeScript |
| Navegação | Bibliotecas de roteamento ou estado | Vue Router ou outras estratégias | Angular Router |

Vite auxilia na execução em desenvolvimento e no processo de build. Pinia oferece uma solução de gerenciamento de estado para Vue, e Axios é uma alternativa para requisições HTTP. A existência desses recursos nos projetos deve ser verificada no código.

Permissões implementadas no front-end não substituem a autorização realizada pelo servidor. Da mesma forma, serviços simulados não comprovam a existência de uma API de produção.

## Metodologia e recursos

Leitura do código-fonte, consulta à documentação e exercícios de comparação entre tecnologias.

## Atividades de revisão

1. Identificar o ponto de entrada e os componentes dos projetos Vue e Angular.
2. Comparar a estrutura desses projetos com o projeto-react.
3. Conferir o arquivo package.json e os comandos de desenvolvimento e build.
4. Identificar a autoria e as condições de uso do template adotado.

As atividades são propostas de revisão, não tarefas oficiais atribuídas ao professor.

## Referências

- [projeto-vue](https://github.com/GilTrindadeJr/projeto-vue)
- [projeto-vue — Vercel (painel do projeto)](https://vercel.com/giltrindadejrs-projects/projeto-vue)
- [projeto-template](https://github.com/GilTrindadeJr/projeto-template)
- [projeto-template — Vercel (painel do projeto)](https://vercel.com/giltrindadejrs-projects/projeto-template)
- [projeto-angular](https://github.com/GilTrindadeJr/projeto-angular)
- [projeto-angular — Vercel (painel do projeto)](https://vercel.com/giltrindadejrs-projects/projeto-angular)
- [projeto-react](https://github.com/GilTrindadeJr/projeto-react)
- [projeto-react — Vercel (painel do projeto)](https://vercel.com/giltrindadejrs-projects/projeto-react)
- [Documentação oficial do Vue](https://vuejs.org/guide/introduction.html)
- [Documentação oficial do Angular](https://angular.dev/)
- [Caderno de Programação Web](./README.md)
