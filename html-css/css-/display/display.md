# Display

- O fluxo do layout no `HTML` ocorre conforme o modo de escrita definida. Por padrão, de cima para baixo e da esqueda para a direita.

## Tipos de valores:

### Inline (`display: inline`)

- Valor padrão. Toda tag nasce como inline.
- Ficam numa linha permitindo que outros elementos inline apareçam ao lado deles.
- **Eles respeitam** as propriedades width, height, margin e padding, **mas não aceitam** margin-top ou margin-bottom, e não pode ter uma largura ou altura especificadas.
- Exemplos comuns são <span>, <a>, <strong>, <em>, <img>, entre outros.

### Block (`display: block`)

- Ocupam toda a largura disponível do elemento pai, não permitindo que outros elementos fiquem ao lado dele.
- **Eles aceitam** width, height, margin e padding personalizados.
- É o estilo inicial de elementos como <h1>, <p>, <div> e outros.

### Inline-block (`display: inline-block`)

- Combina as características de elementos inline e block.
- Como elementos inline, eles fluem dentro do conteúdo na mesma linha, mas como elementos block, aceitam largura, altura, margens e preenchimentos.
- “Respeitam” o elemento pai e não vazam dele.
- Útil para elementos que precisam ser visualmente inline, mas comportar-se como block

### None (`display: none`)

- Remove completamente o elemento do layout da página.
- O espaço que o elemento ocuparia é removido, não sendo reservado na renderização da página.
- Útil para ocultar elementos temporariamente, por exemplo, com JavaScript.

## Span

- Tag genérica que não possio nenhum estilo pré-definido/semântica. É equivalente a uma `div`, mas sem o display block.
