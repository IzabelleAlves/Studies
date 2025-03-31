## No Vue, a declaração de variáveis reativas pode ser feita de duas formas principais:

1. `ref():`

- Usado para qualquer tipo de valor (números, strings, booleanos, arrays, objetos, etc.). Ele cria uma referência reativa, e o valor pode ser acessado ou atualizado por meio da propriedade `.value`.

```vue
<script setup>
import { ref } from "vue";

const contador = ref(0); // Número reativo
const nome = ref("Izabelle"); // String reativa

const incrementar = () => {
  contador.value++; // Atualizando o valor SEMPRE com .value
};
</script>

<template>
  <p>Contador: {{ contador }}</p>
  <button @click="incrementar">Incrementar</button>
  <p>Nome: {{ nome }}</p>
</template>
```

2. `reactive({}):`

- Usado especificamente para objetos que contêm múltiplas
  propriedades reativas. Diferente do `ref()`, as propriedades de um objeto criado
  com `reactive()` podem ser acessadas diretamente sem precisar de `.value`.
- Não é só para valores que serão iterados, mas sim para objetos em geral.

```vue
<script setup>
import { reactive } from "vue";

const usuario = reactive({
  nome: "Izabelle",
  idade: 20,
});

const envelhecer = () => {
  usuario.idade++; // Não precisa de .value. Se acessa igual um object no js
};
</script>

<template>
  <p>Nome: {{ usuario.nome }}</p>
  <p>Idade: {{ usuario.idade }}</p>
  <button @click="envelhecer">Fazer Aniversário</button>
</template>
```

> Se precisar alterar um número ou string diretamente, `ref()` é a melhor opção.  
> Se for um objeto com várias propriedades, `reactive()` faz mais sentido.

### Exemplo de `ref()` e `reactive({})`

```vue
<script setup>
import { ref, reactive } from "vue";

const contador = ref(0); // ref para números
const nome = ref("Izabelle"); // ref para string

const usuario = reactive({
  nome: "Izabelle",
  idade: 20,
}); // reactive para objetos

const incrementar = () => contador.value++; // ref precisa de .value
const envelhecer = () => usuario.idade++; // reactive não precisa de .value
</script>

<template>
  <p>Contador: {{ contador }}</p>
  <button @click="incrementar">Incrementar</button>

  <p>Nome: {{ usuario.nome }}</p>
  <p>Idade: {{ usuario.idade }}</p>
  <button @click="envelhecer">Fazer Aniversário</button>
</template>
```
