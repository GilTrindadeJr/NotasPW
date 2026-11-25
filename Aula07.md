# Aula 07 — Front-end e Back-end — Integração com API de Data e Hora

**Professor da disciplina:** Me. Deivison S. Takatu

> Registro temático de revisão. A numeração possui finalidade organizacional e não representa uma aula oficial ou data confirmada.

## Resumo

O conteúdo relaciona a construção de interfaces web à comunicação com um serviço externo. Os projetos api-data-hora e frontend-data-hora são utilizados como referências para revisar a integração entre o front-end e o back-end. Os conceitos de CRUD permanecem como complemento teórico, pois não há confirmação de que esses projetos implementem operações de cadastro, edição ou exclusão.

## Objetivos de aprendizagem

- Diferenciar as responsabilidades do front-end e do back-end.
- Compreender requisições HTTP e o processamento de dados JSON.
- Relacionar a atualização da interface ao recebimento de dados de uma API.
- Conhecer as operações CRUD e a diferença entre consulta e alteração de registros.

## Conteúdo principal

- Organização de uma aplicação cliente-servidor.
- Interface Vue e API JavaScript.
- Requisições assíncronas e apresentação de dados.
- Métodos HTTP e códigos de resposta.
- JSON.stringify, Content-Type e identificação de registros em APIs que recebem dados.
- Conceitos de CRUD: criação, leitura, atualização e exclusão.
- Estados de carregamento e tratamento de erros.
- Ambiente de desenvolvimento e publicação.

## Aplicação prática nos projetos

O repositório api-data-hora está relacionado à implementação de uma API em JavaScript. O frontend-data-hora é identificado como um projeto Vue associado à apresentação de informações de data e hora.

A divisão em dois repositórios permite estudar separadamente a implementação do serviço e a construção da interface. O fluxo conceitual de integração é:

```text
Interface Vue
    -> Requisição HTTP
    -> API de data e hora
    -> Resposta do serviço
    -> Processamento e atualização da interface
```

Esse fluxo é uma representação didática. A rota, a estrutura da resposta, as bibliotecas de comunicação e a eventual hospedagem devem ser conferidas nos arquivos dos dois projetos.

## Operações CRUD e HTTP

| Operação | Método geralmente associado | Finalidade |
| --- | --- | --- |
| Create | POST | Criar um registro |
| Read | GET | Consultar informações |
| Update | PUT ou PATCH | Atualizar um registro |
| Delete | DELETE | Excluir um registro |

Uma API que apenas oferece informações de data e hora pode não precisar de banco de dados ou de operações completas de CRUD. Não é possível concluir que tais recursos estejam implementados apenas pelo nome do repositório.

## Metodologia e recursos

Leitura de código-fonte, revisão da documentação e exercícios de integração.

## Atividades de revisão

1. Conferir os comandos de instalação e execução dos dois projetos.
2. Identificar a rota e o formato de resposta da API.
3. Verificar a apresentação dos dados na interface Vue.
4. Testar o tratamento de erros em ambiente autorizado.
5. Diferenciar uma API de consulta de um sistema CRUD completo.

As atividades são propostas de revisão, não tarefas oficiais atribuídas ao professor.

## Referências

- [api-data-hora](https://github.com/GilTrindadeJr/api-data-hora)
- [frontend-data-hora](https://github.com/GilTrindadeJr/frontend-data-hora)
- [frontend-data-hora — Vercel (painel do projeto)](https://vercel.com/giltrindadejrs-projects/frontend-data-hora)
- [Documentação da Fetch API](https://developer.mozilla.org/pt-BR/docs/Web/API/Fetch_API)
- [Documentação do Vue](https://vuejs.org/guide/introduction.html)
- [Caderno de Programação Web](./README.md)
