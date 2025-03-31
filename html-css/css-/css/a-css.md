# Cascading Style Sheets (CSS)

- Linguagem de estilo.
- Define o estilo do documento.
- Estrutura básica:

![estrutura css](../assets/imagens/estrutura-css.png)

## Seletor

- O seletor no `CSS` é usado para selecionar elementos `HTML` específicos que queremos estilizar.

```css
h1 {
  color: blue;
}
```

### Tipos de seletores:

- **Tag**: Seleciona elementos pela tag HTML (ex.: `h1`, `p`).
- **Classe**: Seleciona elementos usando um ponto seguido do nome da classe (ex.: `.classe`).
- **ID**: Seleciona elementos pelo ID (único) usando o símbolo `#` (ex.: `#id`).
- **Atributo**: Seleciona elementos com base em atributos específicos (ex.: `[type="text"]`).
- **Combinadores**: Selecionam elementos com base em sua relação com outros (ex.: descendentes, filhos diretos, etc.).

## Link

- Cria uma relação entre um documento `HTML` e um arquivo de estilo `CSS`.
- É adicionado dentro do `<Head>`.

## Rel

- Define o topo de arquivo (stylesheel para CSS). É possíveç linkar outros também como favicons.

## Href

- Define o caminho (URL) para o arquivo que será vinculado. Pode ser um caminho **relativo** (dentro do projeto) ou **absoluto** (URL completa)

**Estrutura do Link do css:**

```html
<link rel="stylesheet" href="styles.css" />
```
