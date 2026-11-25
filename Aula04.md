# Aula 04 — APIs — HTTP, JSON e Operações Assíncronas

**Professor da disciplina:** Me. Deivison S. Takatu

> Registro temático de revisão. A numeração possui finalidade organizacional e não representa uma aula oficial ou data confirmada.

## Resumo

O conteúdo aborda a comunicação entre aplicações, o envio de requisições e o processamento de respostas externas. Os repositórios api-data-hora e frontend-data-hora são referências para o estudo da separação entre uma API e a interface que consome seus dados.

## Objetivos de aprendizagem

- Compreender os fundamentos das APIs e da comunicação cliente-servidor.
- Identificar o papel do front-end e do back-end.
- Relacionar HTTP, JSON e assincronismo ao desenvolvimento web.

## Conteúdo principal

- Cliente, servidor, URL e endpoint.
- HTTP e métodos GET, POST, PUT e DELETE.
- Códigos de status HTTP.
- JSON e representação de dados.
- Fetch API, Promises e async/await.
- Tratamento de exceções com try/catch/finally.
- Validação, indicadores de carregamento e tratamento de falhas.
- CORS e as regras de acesso entre origens no navegador.

## Aplicação prática nos projetos

O repositório api-data-hora é identificado como um projeto JavaScript relacionado a uma API de data e hora. O frontend-data-hora utiliza Vue e representa a parte de interface relacionada a esse conteúdo.

Esses projetos permitem revisar o conceito de cliente-servidor: a API disponibiliza dados por meio de uma interface de comunicação, enquanto o front-end pode solicitar esses dados, interpretar a resposta e apresentá-los ao usuário.

## Comunicação HTTP

| Conceito | Finalidade |
| --- | --- |
| GET | Consultar um recurso |
| POST | Enviar dados para processamento ou criação |
| PUT | Substituir ou atualizar um recurso conforme o contrato da API |
| DELETE | Solicitar a remoção de um recurso |
| JSON | Representar dados de forma estruturada |
| Status HTTP | Informar o resultado de uma requisição |

Exemplo didático de consumo de uma API, sem representar um endpoint confirmado do projeto:

```javascript
async function consultarApi(url) {
    const resposta = await fetch(url);
    if (!resposta.ok) throw new Error('Erro na consulta');
    return await resposta.json();
}
```

A Fetch API não rejeita automaticamente a Promise em todos os erros HTTP. Por isso, é importante verificar resposta.ok. O tratamento de falhas também deve considerar problemas de conexão e respostas inesperadas.

## Metodologia e recursos

Leitura de código-fonte, documentação técnica e exercícios de implementação.

## Atividades de revisão

1. Identificar a rota de consulta oferecida pela API de data e hora.
2. Conferir o formato da resposta e o método HTTP utilizado.
3. Exibir os dados retornados na interface.
4. Testar o comportamento diante de falhas de conexão ou respostas inválidas.

As atividades são propostas de revisão, não tarefas oficiais atribuídas ao professor. Os endpoints, bibliotecas e formatos de resposta devem ser conferidos no código dos projetos.

## Referências

- [api-data-hora](https://github.com/GilTrindadeJr/api-data-hora)
- [frontend-data-hora](https://github.com/GilTrindadeJr/frontend-data-hora)
- [frontend-data-hora — Vercel (painel do projeto)](https://vercel.com/giltrindadejrs-projects/frontend-data-hora)
- [Documentação da Fetch API](https://developer.mozilla.org/pt-BR/docs/Web/API/Fetch_API)
- [Caderno de Programação Web](./README.md)
