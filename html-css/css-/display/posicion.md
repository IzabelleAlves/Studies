# Position

- **Position Fixed**: Fixa o elemento em um local específico na tela, independentemente do scroll. Aceita os valores `top`, `left`, `right` e `bottom`.

- **Position Relative**: Posiciona o elemento de forma relativa ao seu elemento pai, dentro do fluxo normal do documento. Mesmo ao ser movido com `top`, `bottom`, `left` ou `right`, **o espaço inicial que ele ocupava continua reservado**.

- **Position Absolute**: **Remove o elemento do fluxo normal do documento, ou seja, ele não ocupa mais seu espaço original**. Diferente do relative, ele é posicionado em relação à tela inteira. Para que seja posicionado em relação ao elemento pai, é preciso o elemento pai tenha _position: relative_. Caso não haja um elemento pai com essa propriedade, ele será posicionado em relação ao body (tela inteira).

> z-index: Muda o eixo de produnfidade dos elementos. O maior sempre fica por cima.
