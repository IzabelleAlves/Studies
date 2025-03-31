# rem

- Unidade relativa ao tamanho da fonte do elemento raiz `html`. Na maioria dos browsers com configuração padrão 1rem = 16px.
- Baseia-se no tamanho da fonte do elemento raiz (html).
- Se o usuário aumentar o tamanho da fonte no navegador, os elementos ajustam-se proporcionalmente ao que foi definido lá.

## A unidade `rem` tem vantagens sobre o `px`

- Se um usuário aumentar o tamanho da fonte no navegador, os elementos em `rem` se adaptam automaticamente.
- Ajustando font-size no html, toda a interface se adapta sem precisar alterar cada valor individualmente.
- Com `rem`, alterar apenas o font-size do html pode redimensionar toda a interface de forma proporcional.

### É interessante usar o `px` quando:

- Os elementos que não precisam ser dimensionáveis, como bordas finas, ícones ou imagens.
- O tamanho precisa ser fixo e absoluto.

# `vh` e `vw`

- `vh` representa o tamanho da altura da tela visível (viewport heigth) e `vw` da largura (viewport width). 100vw = 100% da tela.

# Porcentagem

- Só atua em relação ao elemento pai. Exemplo: um span que ta numa div e tem 100% de altura. Não ficará com 100% de altura da tela, e sim 100% em relação à altura do elemento pai.
