# Aula 03 — JavaScript Puro — Interatividade, DOM e Eventos

**Professor da disciplina:** Me. Deivison S. Takatu

> Registro temático de revisão. A numeração possui finalidade organizacional e não representa uma aula oficial ou data confirmada.

## Resumo

O conteúdo aborda a implementação de comportamentos interativos e a atualização dos elementos de uma página por meio do JavaScript. O projeto PW é uma referência proposta para relacionar os conceitos à prática.

## Objetivos de aprendizagem

- Compreender os fundamentos de JavaScript puro.
- Identificar operações de manipulação do DOM e tratamento de eventos.
- Aplicar estruturas de dados e funções na construção de aplicações web.

## Conteúdo principal

- Declaração de variáveis com let e const.
- Funções, arrays, objetos e estruturas condicionais.
- Métodos map e forEach.
- Seleção de elementos com getElementById e querySelectorAll.
- Eventos de clique, classList e textContent.
- Gerenciamento do estado da aplicação.
- Temporizadores com setTimeout e setInterval.
- Armazenamento com localStorage e introdução à Web Audio API.

## Aplicação prática e leitura técnica

Ao analisar o projeto PW, é possível procurar referências aos elementos HTML, funções responsáveis pelas interações, eventos e informações mantidas durante a execução. A organização exata dessas funcionalidades deve ser verificada no código.

No JavaScript puro, a interface pode ser modificada diretamente por meio do DOM. A troca de classes CSS, por exemplo, permite alterar a aparência e a visibilidade de elementos sem carregar um novo documento.

Exemplo didático de alteração de estado visual:

```javascript
function mostrarTela(telas, telaSelecionada) {
    telas.forEach(tela => tela.classList.remove('active'));
    telaSelecionada.classList.add('active');
}
```

O exemplo demonstra o uso de funções, coleções e classList. Não corresponde necessariamente a uma implementação existente no projeto.

O localStorage permite armazenar valores associados à origem da página. Como os valores são armazenados em formato textual, pode ser necessário convertê-los com parseInt ou utilizar JSON para representar estruturas mais complexas.

O evento DOMContentLoaded pode iniciar a lógica após a leitura do documento HTML. Já clearInterval permite interromper temporizadores que não são mais necessários.

## Metodologia e recursos

Estudo do código-fonte, consulta à documentação e exercícios práticos.

## Atividades de revisão

1. Implementar um contador de pontos e alternar telas com botões.
2. Armazenar e recuperar um valor com localStorage.
3. Verificar as referências aos arquivos JavaScript no HTML.

As atividades são propostas de revisão, não tarefas oficiais atribuídas ao professor.

## Referências

- [Projeto PW](https://github.com/GilTrindadeJr/PW)
- [Documentação de JavaScript](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript)
- [Caderno de Programação Web](./README.md)
