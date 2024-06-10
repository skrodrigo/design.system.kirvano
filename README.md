Documentação do Projeto Micro-FrameWork em Sass

José Rodrigo de Carvalho <br/>
Edimar Gabriel Marques Mina <br/>
Paulo Cesar Oliveira Souza <br/>

Site base: <a href='https://kirvano.com'/>

O Kirvano é uma plataforma de pagamentos e soluções para negócios online. Ele
oferece ferramentas para produtores digitais, afiliados e prestadores de serviços. 


---------------------------------------------------------------------------------

Construção do Micro Framework 

- Mixins
```
  @mixin flex
  @mixin flex {
   display: flex;
   justify-content: center;
   align-items: center;
  }
```
• Descrição: Este mixin aplica a propriedade display: flex para criar um contêiner
flexível com alinhamento central tanto horizontal quanto vertical.

```
@mixin flex-col {
 display: flex;
 flex-direction: column;
 justify-content: center;
 align-items: center;
}

```
• Descrição: Este mixin cria um contêiner flexível com direção de coluna (itens
empilhados verticalmente) e alinhamento central.

```
@mixin flex-start {
 display: flex;
 justify-content: flex-start;
 align-items: flex-start;
}

```
• Descrição: Este mixin cria um contêiner flexível com alinhamento à esquerda
(horizontal) e ao topo (vertical).
```
@mixin flex-end {
 display: flex;
 justify-content: flex-end;
 align-items: flex-end;
}

```
• Descrição: Este mixin cria um contêiner flexível com alinhamento à direita
(horizontal) e à base (vertical).

Variáveis de texto para importação

- text

```
$text-white: #FFFFFF;
$text-black: #000000;
$text-prima: #171717;
$text-seco: #212121;
$text-terce: #474747;

```
• Estas são variáveis armazenadas usadas para armazenar cores de texto!
Variáveis de background-color para importação

```
$bg-prima: #FFFFFF;
$bg-seco: #212121;
$bg-terce: #474747;
$color-green: #1DA56C;
$color-blue: #0D6EDE;

```
• Variáveis usadas para armazenar cores de fundo do site!

Funções

```
@function toRem($tamanhoPx){
 $root: 16;
 @return $tamanhoPx / $root * 1rem;
}

```
- Código feito para definir o tamanho do pixel padrão!

- Rotas para importação

```
@use './utilities/global.scss';
@use './utilities/mixins' ;
@use './utilities/variables' ;
@use './utilities/functions';
@use './base/displays';
@use './base/texts.scss';
@use './base/spaces.scss';
@use './components/card-title.scss';
@use './components/card-alert.scss';
@use './components/buttons.scss';
@use './components/simple-card.scss';
@use './components/feature-card.scss';
@use './components/top-nav.scss';
@use './components/call-card';
@use './components/footer';
@use './components/plus-card';

```

• Essas são as rotas utilizadas para chamar as variáveis em outras pastas!

```

@use '../utilities/variables' as var;
@use '../utilities/functions' as fn;

```

• Forma correta para importação das variáveis

```
.title-1-white{
 font-size: fn.toRem(52);
 font-weight: 900;
 color: var.$text-white;
 text-align: center;
}

```

```
.title-1-black{
 font-size: fn.toRem(52);
 font-weight: 900;
 color: var.$text-prima;
 text-align: center;
}

```

```
.title-2-white{
 font-size: fn.toRem(32);
 font-weight: 900;
 color: var.$text-white;
 text-align: center;
}

```

```

.title-2-black{
 font-size: fn.toRem(32);
 font-weight: 900;
 color: var.$text-prima;
 text-align: center;
}

```

```
.title-3-white{
 font-size: fn.toRem(24);
 font-weight: 700;
 color: var.$text-white;
 text-align: center;
}
```

```
.title-3-black{
 font-size: fn.toRem(24);
 font-weight: 700;
 color: var.$text-prima;
 text-align: center;
}

```

• Títulos para importação com tamanhos e cores variados, escolha o que melhor
se encaixa no seu código!

```
.paragraph-1-white{
 font-size: fn.toRem(20);
 font-weight: 700;
 color: var.$text-white;
 text-align: center;
}

```

```
.paragraph-1-black{
 font-size: fn.toRem(20);
 font-weight: 700;
 color: var.$text-prima;
 text-align: center;
}

```

```

.paragraph-2-white{
 font-size: fn.toRem(16);
 font-weight: 700;
 color: var.$text-white;
 text-align: center;
}

```

```

.paragraph-2-black{
 font-size: fn.toRem(16);
 font-weight: 700;
 color: var.$text-prima;
 text-align: center;
}

```

```

.paragraph-3-white{
 font-size: fn.toRem(16);
 font-weight: 500;
 color: var.$text-white;
 text-align: center;
}

```

```
.paragraph-3-black{
 font-size: fn.toRem(16);
 font-weight: 500;
 color: var.$text-prima;
 text-align: center;
}

```


• Parágrafos com tamanho e cor variados, para se enquadrar exatamente com o
título!

VARIAVEIS DOS BOTÕES

```
.button-small {
 @include mx.flex;
 border-radius: fn.toRem(10);
 padding: 9px 44px;
 font-size: fn.toRem(14);
 font-weight: 700;
 color: var.$text-white;
 background-color: var.$color-blue;
 cursor: pointer;
 border-style: none;

```
• Botão pequeno para ser importado

```

.button-big {
 @include mx.flex;
 border-radius: fn.toRem(10);
 padding: 9px 88px;
 font-size: fn.toRem(16);
 font-weight: 700;
 color: var.$text-white;
 background-color: var.$color-blue;
 cursor: pointer;
 border-style: none;

```
• Botão grande para ser importado para o código

```
.button-large {
 @include mx.flex;
 border-radius: fn.toRem(10);
 padding: 18px 88px;
 font-size: fn.toRem(16);
 font-weight: 700;
 color: var.$text-white;
 background-color: var.$color-blue;
 cursor: pointer;
 border-style: none;

```
• Botão largo para ser importado no seu código

```

.button-link-small {
 @include mx.flex;
 background-color: transparent;
 border-radius: fn.toRem(10);
 font-size: fn.toRem(14);
 font-weight: 700;
 color: var.$color-blue;
 cursor: pointer;
 border-style: none;
 text-decoration: underline;

```
• Botão pequeno e podendo conter um link nele!

```
.button-link-big {
 @include mx.flex;
 background-color: transparent;
 border-radius: fn.toRem(10);
 font-size: fn.toRem(16);
 font-weight: 700;
 color: var.$color-blue;
 cursor: pointer;
 border-style: none;
 text-decoration: underline;

```
• Botão grande e podendo conter um link nele!

Cartões para chamada de ação

```
.call-card{
 margin: 10px 0px;
 gap: 30px;
 margin: 0 auto;
 @include mx.grid-col-3;
 border-radius: 10px;
 padding: 20px;
 background-color: var.$bg-seco;
 width: 633px;
 height: 267px;
}
```
```
• Cartão para chamada de ação!
.call-card-box{
 @include mx.flex;
 width: 214px;
 height: 201px;
 background-color: var.$bg-terce;
 border-radius: 10px;
}

```

```
• Cartão em formato box para ser importado!
.card-alert {
 @include mx.flex-col;
 max-width: fn.toRem(1216);
 gap: 30px;
 margin: 0 auto;
}

```

```
.border-card-alert {
 border: 1px solid var.$text-terce;
 border-radius: 10px;
 width: 500px;
 padding: 10px;
}
```


• Cartões de alerta, um sem borda e o outro tendo bordas e tamanhos variado

```
.card-title {
 @include mx.flex-col;
 max-width: fn.toRem(1216);
 margin: 0 auto;
}

```
• Cartão do título, podendo ser incluído nas suas principais frases de destaque!

```
.feature-card {
 border: 1px solid var.$text-terce;
 border-radius: 10px;
 width: 600px;
 height: 300px;
 padding: 10px;
 margin: auto;
 @include mx.grid-col-2;
}

```

• Este código cria um elemento de cartão estilizado com borda, cantos
arredondados, dimensões específicas, preenchimento e provavelmente
posicionamento centralizado dentro de seu contêiner

```
.bg-footer{
 background-color: var.$bg-seco;
 bottom: 0;
 width: 100%;
}

```

```
.footer-content{
 margin: 0 auto;
 @include mx.grid-col-1-3;
 max-width: fn.toRem(1216);

```

• Este código cria uma seção de rodapé estilizada com um plano de fundo
colorido posicionado na parte inferior da página.

```
.plus-card{
 gap: 10px;
 padding: 20px;
 margin: 0 auto;
 @include mx.flex-col;
 border: 1px solid var.$text-terce;
 border-radius: 10px;
 width: 380px;
 height: 300px;
 text-align: justify !important;
}

```
• Este código cria um cartão com um layout flexbox em coluna, espaçamento
entre elementos filho, preenchimento interno, borda com cor definida por uma
variável, cantos arredondados, dimensões específicas de largura e altura, e
texto alinhado justificadamente dentro do cartão

```
.simple-card {
 margin: 10px 0px;
 @include mx.flex;
 background-color: transparent;
 color: var.$text-prima;
 gap: fn.toRem(24)
}

```

• Este código cria um cartão simples com layout flexbox, margem vertical, fundo
transparente, cor de texto definida por uma variável e espaçamento entre os
elementos filho.

```
.top-nav-bg{
 background-color: var.$bg-prima;
 @include mx.shadow;
 position: fixed;
 width: 100%;
}
```

```
.top-nav {
 @include mx.flex-between;
 padding: 10px;
 max-width: fn.toRem(1216);
 margin: 0 auto;
 top: 0;
 left: 0;
 right: 0;
 z-index: 1000;
}

```

```
.ul-nav {
 cursor: pointer;
 @include mx.ul;
 @include mx.flex;
 gap: fn.toRem(24);
}

```
• Este código cria uma barra de navegação superior fixa com fundo
personalizado, sombra (definida pelo mixin), layout flexbox para
posicionamento dos itens, preenchimento interno, centralizada
horizontalmente, e possivelmente com itens da lista de navegação alinhados e
espaçados usando flexbox.
