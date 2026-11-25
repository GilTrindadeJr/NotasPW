# Aula 06 — React — Miniaplicações e Lógica de Programação

**Professor da disciplina:** Me. Deivison S. Takatu

> Registro temático de revisão. A numeração possui finalidade organizacional e não representa uma aula oficial ou data confirmada.

## Resumo

O conteúdo aborda o uso de estruturas de dados e gerenciamento de estado na resolução de problemas interativos. O projeto-react, descrito como uma aplicação com cinco funcionalidades, serve de referência para revisar a organização de miniaplicações.

## Objetivos de aprendizagem

- Aplicar fundamentos do React em problemas interativos.
- Compreender operações com arrays e atualização de estado.
- Relacionar os algoritmos à construção e manutenção de aplicações web.

## Conteúdo principal

Os seguintes exemplos são propostas de revisão do conteúdo original, não uma identificação confirmada das cinco funcionalidades do repositório:

- Lista de tarefas: inclusão, conclusão e exclusão com map, filter e spread.
- Contador: incremento e reinicialização do estado.
- Jogo da velha: array de nove posições, combinações vencedoras, empate e alternância.
- Calculadora: entradas, operações e tratamento de erros.
- Consultor de CEP: validação e consulta assíncrona.
- Atualização imutável de arrays.

## Aplicação prática no projeto

A análise do projeto-react deve identificar suas cinco funcionalidades, a estrutura de componentes, os estados necessários e os algoritmos utilizados. A descrição disponível confirma a quantidade de funcionalidades, mas não especifica quais são elas.

## Exemplos didáticos de lógica

| Ferramenta | Estado possível | Operações |
| --- | --- | --- |
| Lista de tarefas | Lista e texto da nova tarefa | Adicionar, concluir e remover |
| Contador | Quantidade de cliques | Incrementar e reiniciar |
| Jogo da velha | Tabuleiro e jogador atual | Jogar, verificar vencedor e reiniciar |
| Calculadora | Expressão ou valores de entrada | Calcular e limpar |
| CEP | Código, endereço, erro e carregamento | Validar e consultar |

A atualização imutável cria uma nova coleção em vez de modificar diretamente o array anterior.

```javascript
setTarefas(tarefas => tarefas.filter(tarefa => tarefa.id !== id));
```

No jogo da velha, oito combinações de três posições podem determinar uma vitória. O empate ocorre quando o tabuleiro está completo e não há vencedor. Na calculadora, um avaliador restrito a expressões matemáticas é preferível à execução de entradas livres com eval. Na consulta de CEP, a entrada pode ser normalizada e validada antes de uma requisição.

## Atividades de revisão

1. Identificar as cinco funcionalidades reais do projeto-react.
2. Revisar as operações de atualização de estado.
3. Verificar entradas vazias e condições inválidas.
4. Elaborar testes correspondentes às funcionalidades implementadas.

## Cenários sugeridos para os exemplos didáticos

| Cenário | Resultado esperado |
| --- | --- |
| Tarefa em branco | Não adicionar o registro |
| Exclusão de tarefa | Remover apenas o ID selecionado |
| Três X na mesma linha | Identificar vitória de X |
| Casa ocupada | Ignorar o movimento |
| CEP inválido | Apresentar mensagem de validação |
| Falha de rede | Informar o erro e finalizar o carregamento |

Esses cenários são sugestões, não resultados de testes executados nem atividades oficiais atribuídas ao professor.

## Referências

- [projeto-react](https://github.com/GilTrindadeJr/projeto-react)
- [projeto-react — Vercel (painel do projeto)](https://vercel.com/giltrindadejrs-projects/projeto-react)
- [React — Atualização de arrays no estado](https://react.dev/learn/updating-arrays-in-state)
- [Caderno de Programação Web](./README.md)
