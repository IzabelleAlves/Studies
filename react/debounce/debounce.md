# Debounce

- O debounce (ou "debouncing") é uma técnica muito usada para controlar a frequência com que uma função é executada, especialmente em eventos que disparam várias vezes em sequência — como digitação (onChange), rolagem (scroll) ou redimensionamento da janela (resize).

## O que o debounce faz?

- Ele espera um tempo determinado depois da última execução para chamar a função. Se a função for chamada de novo antes do tempo acabar, ele reseta o timer.

### Exemplo:

- Imagine um campo de busca que faz uma chamada à API toda vez que o usuário digita algo:

**_Sem debounce:_**

Cada tecla pressionada dispara uma requisição. Isso pode sobrecarregar o sistema e gerar má performance.

**_Com debounce:_**

A função de busca só será chamada depois que o usuário parar de digitar por X milissegundos.

- Como usar useDebounce no React?
  Você pode usar uma função personalizada (hook) assim:

```tsx
import { useState, useEffect } from "react";

function useDebounce<T>(value: T, delay: number): T {
  const [debouncedValue, setDebouncedValue] = useState(value);

  useEffect(() => {
    const timer = setTimeout(() => {
      setDebouncedValue(value);
    }, delay);

    // Limpa o timer se o value mudar antes do delay
    return () => clearTimeout(timer);
  }, [value, delay]);

  return debouncedValue;
}
```

- Como usar o hook:

```tsx
const [search, setSearch] = useState("");
const debouncedSearch = useDebounce(search, 500); // 500ms

useEffect(() => {
  if (debouncedSearch) {
    // fazer a chamada de API com debouncedSearch
  }
}, [debouncedSearch]);
```

- O debounce é basicamente um uso mais elaborado e inteligente do setTimeout.

- Como o debounce funciona por trás:
  Ele utiliza setTimeout para esperar um tempo antes de executar uma função, e clearTimeout para cancelar a execução anterior se o evento acontecer novamente antes do tempo terminar.

**_Um exemplo simplificado de debounce com setTimeout puro:_**

```ts
function debounce(func: Function, delay: number) {
  let timeoutId: ReturnType<typeof setTimeout>;

  return function (...args: any[]) {
    clearTimeout(timeoutId); // limpa o timer anterior
    timeoutId = setTimeout(() => {
      func(...args); // executa a função após o delay
    }, delay);
  };
}
```

- Usando:

```ts
const logSearch = (value: string) => {
console.log('Buscando por:', value);
};

const debouncedLogSearch = debounce(logSearch, 500);

input.addEventListener('input', (e) => {
debouncedLogSearch((e.target as HTMLInputElement).value);
});
Ou seja, sim, o debounce é como um setTimeout com um controle extra para evitar execuções desnecessárias. Ideal quando você quer esperar o "usuário parar de digitar" antes de reagir.

```
