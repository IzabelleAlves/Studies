# react-query

- O React Query é uma biblioteca que facilita o gerenciamento de dados que vêm do servidor (como requisições à API) em aplicações React.
  - Enquanto o estado do React (useState, useReducer) lida com estado local, o React Query gerencia o estado do servidor.

## Estado do servidor

É o dado que vem de uma API ou banco externo (como usuários, produtos, posts...). Diferente do estado local, você não controla diretamente — precisa buscar, armazenar em cache (para evitar requisições desenecessárias), lidar com falhas de rede etc.

## QueryClient

- É o cliente principal que gerencia todas as queries e mutations. Ele é como o "cérebro" do React Query.
- É preciso criar e fornecer um QueryClient no topo da aplicação:

```tsx
import { QueryClient, QueryClientProvider } from "react-query";

const queryClient = new QueryClient(); // pode passar configurações aqui, como defaultOptions, staleTime, retry

function App() {
  return (
    <QueryClientProvider client={queryClient}>
      <YourAppComponents />
    </QueryClientProvider>
  );
}
```

## Query Key

- Um identificador para a requisição. Essa Query Key serve para que o React Query possa fazer o controle da requisição de forma única e não se confundir fazendo fetchs duplicados. Por exemplo, ao ter dois componentes usando a mesma Query Key, garantimos que só sera feito um fetch.

## Função fetch

- No segundo parâmetro passamos a função que é responsável pelo fetch, essa função retornara uma Promise e o useQuery enviara esse resultado para a constante “data”.
- Com isso já conseguimos usar o React Query, porém, ainda tem muito mais a se aproveitar da biblioteca.

## refetchOnWindowFocus

- Essa propriedade vem true como padrão e é responsável por fazer o fetch sempre que o usuário sai e volta para a tela de navegação. Sendo assim, muito útil para atualizar os dados somente quando o usuário está efetivamente usando o app.

# retry

Serve para tentar o fetch mais de uma vez, pode ser usado para evitar problemas causados por erros de conexão. Ele vem por padrão como 3, porém, também pode receber valores boleanos como true e false. Quando true ele tenta infinitamente até conseguir, quando false ele não tenta mais que uma vez. No nosso exemplo, o retry foi usado para garantir que ele tente o fetch, por, no máximo, 6 vezes antes de retornar o erro.

## refetchInterval

Chamado também de polling, o refetchInterval é responsável por fazer o fetch de maneira periódica. No nosso exemplo, estamos tentando o fazer fetch a cada 1 segundo. Essa propriedade pode ser usada quando precisamos dos dados sendo atualizados constantemente, como, por exemplo, um fetch que retorna o horário atual.

## onSuccess

Nessa propriedade passamos uma função que será chamada quando a requisição tiver sido feita com sucesso, no nosso caso, chamamos uma função anonima somente para fazer um console.log da constante “data”.

## onError

É uma propriedade que passamos uma função que sera chamada quando ocorre um erro na requisição, no exemplo usamos para dar um console.log da constante “data” também.

## Revalidação Baseada em Tempo e Revalidação sob demanda

- **Revalidação Baseada em Tempo**: Revalidar dados após um determinado período de tempo e uma nova solicitação ser feita. Isso é útil para dados que mudam com pouca frequência e cuja atualização não é tão crítica.
- Define o tempo de vida útil do cache de um recurso (em segundos).

```tsx
export default async function PostsPage() {
  const res = await fetch("https://api.exemplo.com/posts", {
    next: { revalidate: 30 },
  });
}
```

- **Revalidação sob demanda**: revalidar dados com base em um evento (por exemplo, envio de formulário). A revalidação sob demanda pode usar uma abordagem baseada em tags ou caminhos para revalidar grupos de dados de uma só vez. Isso é útil quando você deseja garantir que os dados mais recentes sejam exibidos o mais rápido possível (por exemplo, quando o conteúdo do seu CMS headless é atualizado).

```tsx
// Server Component
export default async function PostsPage() {
  const res = await fetch("https://api.exemplo.com/posts", {
    next: {
      tags: ["posts"], // ⬅️ aqui está a tag
    },
  });

  const posts = await res.json();

  return (
    <div>
      <h1>Lista de Posts</h1>
      <ul>
        {posts.map((post) => (
          <li key={post.id}>{post.title}</li>
        ))}
      </ul>
    </div>
  );
}
// API Route (Server Action ou Route Handler)
import { revalidateTag } from "next/cache";

export async function POST() {
  revalidateTag("posts"); // ⬅️ Invalida o cache com essa tag
  //Apagar o que estava guardado no cache com aquela tag e forçar um novo fetch() da fonte original de dados

  return Response.json({ revalidated: true });
}
```
