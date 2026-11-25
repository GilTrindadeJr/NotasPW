# Aula 05 — React — Componentes, JSX e Gerenciamento de Estado

**Professor da disciplina:** Me. Deivison S. Takatu

> Registro temático de revisão. A numeração possui finalidade organizacional e não representa uma aula oficial ou data confirmada.

## Resumo

O conteúdo apresenta a construção de interfaces declarativas e a atualização de componentes conforme mudanças no estado da aplicação. Os conceitos são relacionados ao projeto-react, descrito como uma aplicação React com cinco funcionalidades.

## Objetivos de aprendizagem

- Assimilar os fundamentos do React.
- Identificar a organização de componentes e o gerenciamento de estado.
- Relacionar esses conhecimentos ao desenvolvimento e à manutenção de aplicações web.

## Conteúdo principal

- Componentes funcionais e JSX.
- Compartilhamento de informações por props.
- Hook useState.
- Eventos onClick e onChange.
- Campos de entrada controlados.
- Renderização condicional, listas e keys.
- Diferenças entre manipulação manual do DOM e renderização declarativa.
- npm e ambientes de desenvolvimento React, incluindo Create React App e Vite.

## Aplicação prática no projeto

O projeto-react reúne cinco funcionalidades e constitui uma referência para estudar como uma aplicação pode organizar diferentes recursos em uma única interface.

A leitura do código deve identificar os componentes existentes, as variáveis de estado, o tratamento das interações e a forma de navegação entre as funcionalidades. O arquivo package.json, quando presente, permite verificar as dependências e os comandos disponíveis.

## Estado e renderização

Exemplo didático de um contador em React:

```jsx
import { useState } from 'react';

function Contador() {
    const [cliques, setCliques] = useState(0);
    return <button onClick={() => setCliques(n => n + 1)}>{cliques}</button>;
}
```

O hook useState disponibiliza o valor atual e uma função para atualizá-lo. O JSX permite inserir expressões JavaScript entre chaves. Quando o estado muda, o React atualiza a interface de maneira declarativa, sem que seja necessário modificar manualmente o texto do botão por getElementById.

Props permitem transmitir informações entre componentes, enquanto keys auxiliam na identificação dos itens de listas. Separar componentes por responsabilidade pode facilitar a manutenção e evitar remontagens desnecessárias.

## Metodologia e recursos

Estudo do código-fonte, consulta à documentação e exercícios de implementação.

## Atividades de revisão

1. Desenvolver um contador com incremento e reinicialização.
2. Construir um componente de menu.
3. Renderizar uma lista com identificadores individuais.
4. Identificar as dependências e os scripts do projeto-react.

As atividades são propostas de revisão, não tarefas oficiais atribuídas ao professor. O exemplo acima é didático; versões, estrutura de arquivos e implementação do projeto devem ser conferidas no repositório.

## Referências

- [projeto-react](https://github.com/GilTrindadeJr/projeto-react)
- [projeto-react — Vercel (painel do projeto)](https://vercel.com/giltrindadejrs-projects/projeto-react)
- [Documentação oficial do React](https://react.dev/learn)
- [Caderno de Programação Web](./README.md)
