# Box Model (Modelo de Caixa)

O **Box Model** é um conceito fundamental no `CSS`, que descreve como os elementos `HTML` são estruturados e como o espaço é distribuído ao redor deles. Cada elemento na página é representado como uma caixa retangular, e o modelo define as áreas dessa caixa e como elas interagem.

## Componentes do Box Model

1. **Content (Conteúdo)**

- A área onde o conteúdo real do elemento, como texto ou imagens, é exibido.
- Exemplo: O texto de um parágrafo ou a imagem dentro de um `img`.

2. **Padding (Preenchimento)**

- O espaço entre o conteúdo do elemento e a borda (border).
- Pode ser usado para criar espaçamento interno.
- Exemplo:

```css
div {
  padding: 20px;
}
```

3. **Border (Borda)**

- A borda que envolve o elemento. Pode ser configurada com diferentes estilos, larguras e cores.
- Exemplo:

```css
div {
  border: 2px solid black;
}
```

4. **Margin (Margem)**

- O espaço fora da borda do elemento, que separa o elemento de outros elementos.
- Exemplo:

```css
div {
  margin: 10px;
}
```

5. **Width (largura)**

- A largura total é o somatório do conteúdo + padding (left/rigth) + bprder (left/rigth)

## Fluxo de Layout

O **Box Model** afeta como o layout do documento é exibido. O tamanho final do elemento (o "box") é a soma do conteúdo, padding, borda e margem. É importante entender como esses componentes interagem para controlar o layout de forma eficaz.

**Modelo:**

![estrutura box-model](../assets/imagens/box-model.png)
