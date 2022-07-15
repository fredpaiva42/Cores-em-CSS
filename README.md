# Aprendendo sobre cores e algumas propriedades no CSS

Imagem final do Projeto:
![](print%20da%20página.png)

Uma maneira de fácil de centralizar um elemento, é com a *propriedade abreviada* `margin`. A propriedade abreviada `margin` facilita a definição de várias áreas de margem ao mesmo tempo.

Exemplo:
```CSS
h1 {
    margin: auto;
}
```
Isso define `margin-top`, `margin-right`, `margin-bottom` e `margin-left` como **auto**.

Quando a propriedade abreviada `margin` tiver dois valores, ela define `margin-top` e `margin-bottom` para o primeiro valor, e `margin-left` e `margin-right` para o segundo valor.

## RGB

Hoje em dia, existem dois modelos de cores: o modelo **aditivo RGB** (vermelho, verde, azul), usado em dispositivos eletrônicos, e o modelo **subtrativo CMYK** (ciano, magenta, amarelo, preto), usado em impressão.

**RGB** é aditivo e isso significa que as cores começam como pretas e mudam quando são introduzidos diferentes níveis de vermelho, verde e azul. 

Uma função é um trecho de código que pode receber uma entrada e executar uma ação específica. A função do CSS `rgb` aceita valores, ou *argumentos*, para vermelho, verde e azul, e produz uma cor:
```css
.marker{
    background-color: rgb(red, green, blue);
}
```
Cada valor vermelho, verde e azul é um número de **0** a **255**. **0** significa que há 0% dessa cor e é preta. **255** significa que há 100% dessa cor.

No modelo aditivo de cor **RGB**, *cores primárias* são cores que, quando combinadas, criam branco puro. Mas para que isso aconteça, cada cor tem que estar em sua maior intensidade.
- Vermelho: `rgb(255, 0, 0)`
- Verde: `rgb(0, 255, 0)`
- Azul: `rgb(0, 0, 255)`

*Cores secundárias* são cores que conseguimos quando combinamos as cores primárias.
- Amarelo: `rgb(255, 255, 0)`
- Ciano: `rgb(0, 255, 255)`
- Magenta: `rgb(255, 0, 255)`

*Cores terciárias* são criadas combinando uma cor primária com uma cor secundária.
- Laranja: `rgb(255, 127, 0)`
- Verde da primavera: `rgb(0, 255, 127)`
- Violeta: `rgb(127, 0, 255)`
- Chartreuse verde: `rgb(127, 255, 0)`
- Azure: `rgb(0, 127, 255)`
- Rosa brilhante: `rgb(255,0, 127)`

O circulo cromático é um circulo onde cores, ou *matizes*, semelhantes ficam próximas e cores diferentes ficam mais distantes. Por exemplo, vermelho puro, está entre as cores rosa e laranja.

Duas cores que são opostas uma da outra na roda de cores são chamadas de *cores complementares*. Se duas cores complementares forem combinadas, produzirão cinza. Mas quando elas são colocadas lado a lado, essas cores produzem um forte contraste visual e parecem mais brilhantes.

Por exemplo se tivermos próximas vermelho e ciano, elas ficam muito brilhantes. No entanto, o forte contraste visual pode ser chocante se for usado demais em um site, e às vezes, pode torna o texto mais difícil de ler se for colocado em um fundo com cores complementares.

É uma prática melhor escolher uma cor como a cor dominante e usar sua cor complementar como um destaque para chamar a atenção para certos conteúdos na página.

## Hexadecimais

Uma maneira muito comum de aplicar cor a um elemento com CSS é com ***hexadecimal*** ou valores hexadecimais. Eles são apenas uma outra forma de valores RGB.

Os valores de cores hexadecimais começam com um caractere `#` e recebem seis caracteres de **0-9** e **A-F**. O primeiro para de caracteres representa vermelho, o segundo par representa verde, e o terceiro representa azul. Por exemplo, #4B5320.

Com cores hexadecimais, **00** é 0% dessa cor e **FF** é 100%. Então, `#00FF00` traduz 0% vermelho, 100% verde e 0% azul, sendo igual a `rgb(0, 255, 0)`.

## HSL

O modelo de cores de **HSL**, ou **matiz, saturação e luz** é outra forma de representar cores.

A função do CSS `hsl` aceita 3 valores: um número de 0 a 360 para o matiz, uma porcentagem de 0 a 100 para saturação e uma porcentagem de 0 a 100 para a luz.

Se imaginarmos um circulo cromático, a cor vermelha fica a 0 graus, verde é a 120 graus e azul a 240 graus.

**Saturação** é a intensidade de uma cor de 0%, ou cinza, até 100% para cor pura.

**Luz** é o nível de brilho no qual uma cor aparece, de 0%, ou preta completa, até 100%, branco total, com 50% de neutralidade.

## Gradiente

Um gradiente é quando uma cor muda para outra. A função CSS `linear-gradient` permite controlar a direção de transição ao longo de uma linha e quais cores são usadas.

Uma coisa a se lembrar é qua função `linear-gradient` realmente criar um elemento `image` e que ela geralmente é pareada com a propriedade `background` que pode aceitar uma imagem como um valor.

Sintaxe da função `linear-gradient`:
```CSS
linear-gradient(gradientDirection, color1, color2, ...);
```
`gradientDirection` é a direção da linha usada para a transição. `color1` e `color2` são argumentos de cor, que são as cores que serão usadas na transição em si. Elas podem ser de qualquer tipo de cor, incluido palavras-chave de cores, hex, `rgb` ou `hsl`.

**Color-stops** permitem que você ajuste onde as cores são colocadas ao longo da linha gradiente. São uma unidade de comprimento como o `px` ou porcentagens que seguem uma cor na função `linear-gradient`.

Por exemplo, neste gradiente vermelho e preto, a transição do vermelho para o preto ocorre no ponto 90% ao longo da linha gradiente. Então o vermelho ocupa a maior parte do espaço disponível: 
```
linear-gradient(90deg, red 90%, black);
```

Para tornar as cores mais realistas, podemos aplicar a direção de `180deg`, color-stops de `0%`, `50%` e `100%`, respectivamente e tons diferentes da mesma cor, para cada argumento de cor na função `linear-gradient`. Os tons no topo e no fundo do marcador serão mais escuros, enquanto o meio ficará mais leve, como se houvesse uma luz acima dele.

Se nenhum argumento `gradientDirection` é fornecido para a função `linear-gradient`, ele organiza as cores de cima para baixo, ou ao longo de uma linha de 180 graus, por padrão.

# Opacidade

**Opacidade** descreve a quantidade de transparência de um elemento. Por exemplo, um muro sólido é opaco, e nenhuma luz pode passar. Mas um copo de bebida é muito mais transparente e pode ver-se através do copo o outro lado.

Com a propriedade do CSS, `opacity`, podemos controlar como um elemento é opaco ou transparente. Com o valor **0**, ou 0% o elemento será completamente transparente e **1.0**, ou 100%, o elemento será completamente opaco, como é padrão.

Outra maneira de definir a opacidade para um elemento é com o *canal alfa*. Semelhante à propriedade `opacity`, o canal alfa controla o nível de transparência ou de opacidade de uma cor.

Para adicionar um canal alfa a uma cor `rgb`, é só usar a função `rgba`. A função `rgba` age como a função `rgb`, mas recebe mais um número de **0** a **1.0** para o canal alfa.
```
rgba(redValue, greenValue, blueValue, alphaValue);
```

## Sombra

A propriedade `box-shadow` aplica uma ou mais sombras a um elemento.

Sintaxe:
```
box-shadow: offsetX offsetY color;
```

As bordas da sombra têm pontas. Isso ocorre porque há um valor opcional de `blurRadius` para a propriedade `box-shadow`:
```
box-shadow: offsetX offsetY blurRadius color;
```
O valor padrão do `blurRadius` é **0** e arestas com pontas. Quanto maior o valor de `blurRadius`, maior será o efeito de desfoque. 

Para expandir ainda mais a sombra tem o valor opcional `spreadRadius`: 
```
box-shadow: offsetX offsetY blurRadius spreadRadius color;
```