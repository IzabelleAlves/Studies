# Ouvintes de Eventos no Vue

No Vue, podemos **ouvir eventos DOM** usando a diretiva **`v-on`**:

## Exemplo básico:

```vue
<button v-on:click="increment">{{ count }}</button>
```

> Forma abreviada:

```vue
<button @click="increment">{{ count }}</button>
```

## Exemplo completo:

```vue
<script setup>
import { ref } from "vue";

const count = ref(0);

function increment() {
  // Atualiza o estado do componente
  count.value++;
}
</script>

<template>
  <button @click="increment">{{ count }}</button>
</template>
```
