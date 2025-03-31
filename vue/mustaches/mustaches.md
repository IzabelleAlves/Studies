# Importância das Chaves `{{ }}` no Vue

As chaves duplas `{{ }}` no Vue são chamadas de **interpolação** e servem para exibir variáveis reativas dentro do template de forma dinâmica.

## Por que são importantes?

1. **Atualização automática**: Se o valor da variável mudar, o Vue reflete a mudança automaticamente na interface.
2. **Código mais limpo**: Permite exibir valores sem precisar manipular diretamente o DOM.
3. **Evita injeção de código malicioso**: O Vue trata os valores como texto puro, prevenindo ataques como XSS.

---

## Exemplo:

```vue
<script setup>
import { ref } from "vue";

const nome = ref("Izabelle");
</script>

<template>
  <p>Olá, {{ nome }}!</p>
</template>
```
