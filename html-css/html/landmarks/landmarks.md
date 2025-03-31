# Landmarks

- Atual de modo similar á uma div. Não mudam em nada o conteúdo/apresentação da página.

1. Main
2. Nav
3. Section
4. Article
5. Aside
6. Footer
7. header

- 1. `<main>` (Conteúdo principal)

  - Contém o conteúdo principal da página, sem incluir cabeçalhos, barras laterais e rodapés.
  - Deve existir apenas um <main> por página.

- 2. `<nav> `(Navegação)

  - Marca um bloco navegação dentro do site.
  - Útil para menus.
  - Indicaod que tenha so um principal.
  - Pode ser identificado com role="navigation".

- 3. `<section>` (Seção de conteúdo)

  - Define uma seção genérica dentro do conteúdo.
  - Pode conter um título <h2>, <h3> etc.

- 4. `<article>` (Conteúdo independente)

  - Contém um bloco de conteúdo autossuficiente, como posts de blog e notícias.

- 5. `<aside>` (Conteúdo secundário)

  - Para informações adicionais que não são essenciais para a compreensão principal da página.
  - Representa informações complementares, como barras laterais e widgets.
  - Pode ser identificado com role="complementary".

- 6. `<footer>` (Rodapé)

  - Contém informações de rodapé, como direitos autorais e links de contato.
  - Pode ser identificado com role="contentinfo".

- 7. `<header>` (Cabeçalho)
  - Representa a introdução ou seção de navegação da página.
  - Pode conter logotipos, menus e títulos principais.
  - Se não for um cabeçalho global, pode ser usado em seções individuais.

## Atributo `aria-label`

- Atributo que começa com 'aria' é um atributo focado em acessibilidade.
- Dá um atributo para a tag
