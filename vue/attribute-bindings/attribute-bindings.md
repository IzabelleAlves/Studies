# Ligações de Atributos no Vue

- Para vincular um atributo a um valor dinâmico, usamos a diretiva **`v-bind`**:

## Exemplo:

```vue
<div v-bind:id="dynamicId"></div>
```

## `v-blind`

- Permite alterar a classe CSS de um elemento com base em uma variável ou expressão do Vue. Isso altera o estilo dependendo do valor da variável.
- A diretiva `v-bind` é usada para associar um valor dinâmico a um atributo. Ela sempre começa com o prefixo `v-` e permite que você use variáveis do componente para atualizar os atributos.
  - quando você usa `v-bind` para a propriedade class (ou outros atributos como style), você pode alterar dinamicamente o estilo de um elemento, como se estivesse manipulando o CSS.
- Pode ser abreviado para `:id=` ou `:class=`

  - Exemplo:

  ```vue
  <div :id="dynamicId"></div>
  <h1 :class="titleClass">Título</h1>
  ```
