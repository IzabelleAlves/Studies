# O que é o React?

- É uma biblioteca usada para criar interfaces de usuário interativas.
- Ele brilha quando há muita interações do usuário dentro da aplicação.
- Componentes. Bloco de códigos como peças de legos que, juntas, formam algo grande.
- Desenvolvido pela Meta.
- Utilizado tanto em iOS quanto em android (React Native) ou Desktop (Electron)

## Componentes

- No React, a aplicação é dividida em pequenos componentes.
- Vários componentes, quando combinados, formam grandes estruturas.
- Pense neles como se fossem peças de LEGO.
- Usa-se JSX para escrevê-los.
- Um componente pe uma função JavaScript que retorna um JSX (HTML misturado com JS)

## Usando o React

- É necessário ter o node instalado na máquina. O node é uma ferramenta que permite que executemos o JavaScript fora do navegador.
- Você instala o node e 'recebe' junto um npm (Node Package Manager), o gerenciador de pacotes do Node.js. Ele permite instalar, gerenciar e compartilhar bibliotecas e ferramentas JavaScript.
- O vite facilita o uso do React e melhora a experiência de desenvolvimento.

### Instalando o vite

```bash
npm creat vite@5.5.2 .
```

- Dessa forma instala uma versão específica do Vite.

* Depois disso, seleciona React e JavaScript.
* npm i -> para instalar todas as dependências.
* npm run dev -> para rodar o projeto.

## O React usa o SPA

- Single Page Aplication, que seria uma página simples para ser o index.html. Tudo que está na página não é adicionado diretamente nela, e sim adicionado pelo JS.
- Traz velocidade: a navegação entre as páginas é muito mais rápida, pois não exige chamadas para um servidor.
- Permite um alto nível de interatividade.
- Experiência do Usuário: SPAs são altamente interativas e performáticas.

## Exportações no React: Default vs Named ✨

### **1. Exportação Padrão (Default Export)**

Quando usamos `export default`, estamos dizendo que o arquivo exporta **apenas um item principal**. Isso permite que o nome do componente seja qualquer um na importação!

**_Exemplo:_**

```jsx
function App() {
  return <h1>Hello World!</h1>;
}

export default App;
```

**_Importando:_**

```jsx
import MeuComponente from "./App"; // Funciona, pois é export default!

<MeuComponente />;
```

Aqui, o nome do componente pode ser qualquer um! `MeuComponente`, `Banana`, `SuperApp`... funciona porque só tem **um item sendo exportado por padrão**.

---

### **2. Exportação Nomeada (Named Export)**

Quando usamos `export` antes da declaração, estamos exportando **de forma nomeada**. Nesse caso, o nome **deve ser mantido na importação**.

**_Exemplo:_**

```jsx
export function App() {
  return <h1>Hello World!</h1>;
}
```

**_Importando:_**

```jsx
import { App } from "./App"; // Tem que usar chaves e o mesmo nome!

<App />;
```

Se tentar importar sem chaves ou com outro nome:

```jsx
import MeuComponente from "./App"; ❌ // Erro!
```

Vai dar erro, porque exportação nomeada **exige o mesmo nome**.

---

### ✨ **3. Exportando no Final do Arquivo**

Também podemos definir a função primeiro e exportar depois:

```jsx
function App() {
  return <h1>Lindaaa</h1>;
}

export { App }; // Exportação nomeada no final
```

A importação continua sendo:

```jsx
import { App } from "./App";
```

- Use **`export default`** quando seu arquivo exporta **apenas um componente principal**. Assim, pode importar com qualquer nome.
- Use **`export { algo }`** quando precisar exportar **múltiplos itens** do mesmo arquivo.

## States (ou, variáveis de Estado)

- No React, o state é um objeto especial que guarda informações sobre um componente e pode mudar ao longo do tempo. - Permite que os componentes sejam dinâmicos e respondam a interações do usuário.
- Armazena valores que podem mudar e, quando isso acontece, o componente re-renderiza automaticamente para refletir a mudança na interface.
- Usamos o hook useState para criar e atualizar o estado.
- Quando eu altero meu state, eu atualizo a tela.
- É uma variável que você altera no react que faz com que o componente seja re-renderizado.
- Útil quando você quer fazer algo em resposta a interação do usuário

```jsx
import { useState } from "react";
//sempre importar o useState

function App() {
  const [message, setMessage] = useState("Olá mundo");
  //Declaro a variável e digo que é um state; Quando eu quiser que ela mude, pgo o setMessage
  return (
    <div>
      <h1>{message}</h1>
      <button
        onClick={() => {
          setMessage("Olá, fui clidado");
        }}
      >
        Mudar mensagem
      </button>
    </div>
  );
}

export default App;
```

## O que é um Hook no React?

- É uma função especial que permite usar recursos do React dentro de componentes funcionais, como state, efeitos colaterais e contexto.

## O que é uma props?

- São uma forma de passar dados de um componente pai para um componente filho. Eles são objetos que contêm valores que podem ser acessados dentro do componente filho.
- O App geralmente é o componente pai principal porque ele é o ponto de entrada da aplicação.
- O elemento pai é o que renderiza tudo. Então o filho é o componente. Se eu adicionar um useState, ele precisará ser adicionado no elemento pai (que é quem renderiza) e passado como props para o elemento filho (componente). O elemento filho não poderá alterar o state do pai, só acessa, o pai quem altera por meio de funções.
- São usadas para passar dados de um componente pai para um componente filho.
- Elas são somente leitura (o componente filho não pode modificar os valores das props recebidas).
- Permitem que os componentes sejam reutilizáveis e dinâmicos.
- Fluxo de dados unidirecional: As informações fluem do pai para o filho, não o contrário.

## Destructuring

- É um recurso do JavaScript que permite extrair valores de objetos ou arrays de forma mais concisa e prática, utilizando uma sintaxe especial. Quando falamos de "destructuring das props", estamos nos referindo à técnica de usar o destructuring para extrair propriedades de um objeto (geralmente, as props passadas para um componente React) de forma direta.
- Suponha que você tenha um componente React que recebe um objeto props com várias propriedades. Em vez de acessar cada propriedade individualmente com props.nome ou props.idade, você pode fazer o destructuring diretamente nas variáveis dentro dos parâmetros da função.

**Exemplo de acesso às props sem o destructurin:**

```jsx
const MeuComponente = (props) => {
  return (
    <div>
      <h1>{props.nome}</h1>
      <p>{props.idade}</p>
    </div>
  );
};
```

**Exemplo de acesso às props com o destructurin:**

```jsx
const MeuComponente = ({ nome, idade }) => {
  return (
    <div>
      <h1>{nome}</h1>
      <p>{idade}</p>
    </div>
  );
};
```

- O destructuring das props é uma prática muito comum em componentes React, especialmente quando você tem várias props para acessar e quer evitar a repetição da palavra 'props'.
