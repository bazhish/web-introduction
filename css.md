# Guia de CSS

## O que é CSS?

CSS (**Cascading Style Sheets**) é a linguagem usada para **estilizar** páginas web.
Enquanto o **HTML** organiza a estrutura do conteúdo, o **CSS** define a aparência: cores, tamanhos, espaçamentos, alinhamentos, animações, responsividade e layout.

### Exemplo simples
#### **css**

```css
p {
  color: blue;
  font-size: 18px;
}
```

Nesse exemplo:
- `p` é o **seletor**
- `color` e `font-size` são **propriedades**
- `blue` e `18px` são **valores**

## CSS inline

Aplicado diretamente no elemento HTML.

#### **html**

```html
<p style="color: red;">Texto vermelho</p>
```

### Vantagem
- rápido para teste

### Desvantagem
- difícil de manter
- mistura estrutura com estilo
- não é profissional para projetos maiores

## CSS Interno

O CSS interno é aplicado adicionando a tag ``<style>`` dentro da seção ``<head>`` de um arquivo HTML específico. Ele permite estilizar elementos da página atual sem arquivos externos, sendo ideal para páginas únicas ou testes rápidos, mas ineficiente para sites grandes devido à repetição de código.

#### **html**

```html
<head>
  <style>
    p {
      color: green;
    }
  </style>
</head>
```

## CSS Externo

O CSS externo é a prática para estilizar paginas, utilizando um arquivo separado com extensão .css vinculado ao HTML via tag ``<link rel = "stylesheet" href = "caminho do arquivo">`` no ``<head>``. Isso separa conteúdo de design, facilitando a manutenção e permitindo aplicar o mesmo estilo em várias páginas, garantindo consistência e carregamento rápido. 

#### **html**

```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

#### **css**

```css
p {
  color: purple;
}
```

### Vantagens
- organização
- reutilização
- manutenção mais fácil
- padrão profissional

# Sintaxe do CSS

#### **css**

```html
seletor {
  propriedade: valor;
}
```



## Seletores e Classes

Seletores são padrões utilizados para identificar e aplicar estilos (como cores, fontes e tamanhos) a elementos HTML específicos em uma página. Eles funcionam como regras de localização, permitindo selecionar elementos por tipo (`tag`), classe, ID ou atributo, sendo essenciais para a estrutura e o design responsivo.

## Seletor por elemento

O primeiro conceito de seletor é o seletores de elemento (ou seletores de tipo/tag) aplicam estilos diretamente a todas as instâncias de uma tag HTML específica (ex: ``p``, ``h1``, ``div``) em uma página. Eles são fundamentais para definir a estilização global ou padrão de elementos, sem precisar de classes ou IDs, utilizando diretamente o nome da tag no CSS.



#### **css**

```css
p {
    color: blue;
}
```
## Seletor por classe

O segundo conceito de seletor é o seletor de classe que é utilizado para estilizar elementos HTML com base no atributo ``class``, sendo precedido por um ponto (``.``). Ele permite aplicar regras a múltiplos elementos, oferecendo alta reutilização e organização, com maior especificidade que seletores de tipo.


#### **html**

```html
<div class="caixa"></div>
```

#### **css**

```css
.caixa {
    background: gray;
}
```

### Observação
- classes podem ser reutilizadas em vários elementos  

## Seletor por ID

O terceiro seletor seria o ID que é é utilizado para estilizar um único elemento HTML exclusivo na página, utilizando o símbolo de cerquilha (#) seguido do nome do ID. Ele possui alta especificidade, tornando-o ideal para elementos singulares.

#### **html**
```html
<h1 id="titulo">Meu título</h1>
```

#### **css**
```css
#titulo {
    color: red;
}
```
## Seletor universal
### **css**
```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

Seleciona todos os elementos, muito usado em reset inicial.

## Seletor de grupo

Um seletor de grupo no CSS (usado para estilizar HTML) permite aplicar o mesmo conjunto de regras a múltiplos elementos ao mesmo tempo, sem precisar repetir o código.
### **css**
```css
h1, h2, p {
  font-family: Arial, sans-serif;
}
```

Aplica o mesmo estilo para vários elementos.


## Seletor descendente
O seletor descendente no CSS, representado por um espaço em branco entre dois seletores (ex: ``div``, ``p``), seleciona todos os elementos filhos, netos ou mais profundos que estão dentro de um elemento ancestral específico. Ele é ideal para aplicar estilos a elementos baseados em sua posição na hierarquia HTML.

### **css**
```css
div p {
  color: green;
}
```

Seleciona todo `<p>` que estiver dentro de uma `<div>`.


## Seletor filho direto
O seletor filho CSS, representado pelo sinal de maior que (``>``), aplica estilos apenas aos filhos diretos de um elemento pai, ignorando netos ou descendentes mais profundos. A sintaxe é pai ``>`` filho ``{ propriedade: valor; }``, garantindo alta precisão e maior especificidade na estilização.
### **css**
```css
div > p {
  color: orange;
}
```

## Propriedades

As propriedades CSS definem **como um elemento será estilizado**.  
Elas controlam cor, tamanho, espaçamento, bordas, alinhamento, posição e muito mais.


## `color`

Define a **cor do texto** de um elemento.

#### **css**

```css
p {
  color: blue;
}
```

---

## `background`

A propriedade `background` é um atalho usado para definir várias configurações de fundo em uma única linha, como:

- cor de fundo
- imagem
- posição
- repetição
- tamanho
- fixação

#### **css**

```css
div {
  background: lightgray;
}
```

#### **css**

```css
div {
  background: url("imagem.jpg") no-repeat center/cover;
}
```

---

## `border`

A propriedade `border` é um atalho para definir:

- espessura da borda
- estilo da borda
- cor da borda

#### **css**

```css
div {
  border: 2px solid black;
}
```

### Estilos de borda

- `dashed`
- `dotted`
- `solid`
- `double`
- `groove`
- `ridge`
- `inset`
- `outset`
- `hidden`
- `none`

### Bordas por lado

Também é possível aplicar borda em lados específicos:

- `border-top`
- `border-right`
- `border-bottom`
- `border-left`

#### **css**

```css
div {
  border-top: 3px solid red;
}
```

### Bordas arredondadas

Para arredondar os cantos da borda, usamos `border-radius`.

#### **css**

```css
div {
  border-radius: 10px;
}
```

---

## `margin`

Define o **espaçamento externo** de um elemento, ou seja, o espaço fora da borda.

#### **css**

```css
div {
  margin: 20px;
}
```

### Lados individuais

- `margin-top`
- `margin-right`
- `margin-bottom`
- `margin-left`

#### **css**

```css
div {
  margin-top: 10px;
}
```

### Observação

O valor `auto` é muito usado para centralizar elementos em alguns casos.

#### **css**

```css
div {
  width: 300px;
  margin: auto;
}
```

---

## `padding`

Define o **espaçamento interno** de um elemento, ou seja, o espaço entre o conteúdo e a borda.

#### **css**

```css
div {
  padding: 20px;
}
```

### Lados individuais

- `padding-top`
- `padding-right`
- `padding-bottom`
- `padding-left`

#### **css**

```css
div {
  padding-left: 15px;
}
```

---

## `width` e `height`

Definem a **largura** e a **altura** da área de conteúdo de um elemento.

#### **css**

```css
div {
  width: 300px;
  height: 150px;
}
```

### Limites máximos

As propriedades `max-width` e `max-height` definem o tamanho máximo que um elemento pode atingir.

#### **css**

```css
img {
  max-width: 100%;
}
```

---

## `text-align`

Define o **alinhamento horizontal do texto** dentro de um elemento.

### Valores principais

- `left`
- `right`
- `center`
- `justify`

#### **css**

```css
p {
  text-align: center;
}
```

---

## `direction`

Define a **direção do texto**.

### Valores principais

- `ltr` = da esquerda para a direita
- `rtl` = da direita para a esquerda

#### **css**

```css
p {
  direction: rtl;
}
```

---

## `text-decoration`

Usada para adicionar ou remover decorações no texto.

### Valores comuns

- `underline`
- `overline`
- `line-through`
- `none`

#### **css**

```css
a {
  text-decoration: none;
}
```

---

## `text-transform`

Controla a capitalização do texto sem alterar o conteúdo original no HTML.

### Valores principais

- `uppercase`
- `lowercase`
- `capitalize`
- `none`

#### **css**

```css
p {
  text-transform: uppercase;
}
```

---

## `letter-spacing`

Define o **espaçamento entre as letras**.

#### **css**

```css
p {
  letter-spacing: 2px;
}
```

---

## `line-height`

Define o **espaçamento entre as linhas** de um texto.

#### **css**

```css
p {
  line-height: 1.6;
}
```

---

## `word-spacing`

Define o **espaçamento entre as palavras**.

#### **css**

```css
p {
  word-spacing: 5px;
}
```

---

## `font`

A propriedade `font` é um atalho para definir várias propriedades da fonte de uma só vez, como:

- `font-style`
- `font-variant`
- `font-weight`
- `font-size`
- `line-height`
- `font-family`

#### **css**

```css
p {
  font: italic small-caps bold 16px/1.5 Arial, sans-serif;
}
```

### Observação

Também é comum usar essas propriedades separadamente.

#### **css**

```css
p {
  font-size: 18px;
  font-family: Arial, sans-serif;
  font-weight: bold;
}
```

---

## `display`

Define como o elemento será exibido no layout da página.

### Valores principais

- `block`
- `inline`
- `inline-block`
- `flex`
- `grid`
- `none`

#### **css**

```css
span {
  display: inline-block;
}
```

### Observação

- `block` ocupa a linha inteira
- `inline` fica na mesma linha de outros elementos
- `inline-block` permite estilizar como bloco sem quebrar linha
- `flex` e `grid` são usados para layout

---

## `position`

Define como o elemento será posicionado na página.

### Valores principais

- `static`
- `relative`
- `absolute`
- `fixed`
- `sticky`

---

### `static`

Valor padrão. O elemento segue o fluxo normal do documento.

#### **css**

```css
div {
  position: static;
}
```

### Observação

Com `static`, propriedades como `top`, `right`, `bottom` e `left` não funcionam.

---

### `relative`

O elemento continua no fluxo normal, mas pode ser deslocado em relação à sua posição original.

#### **css**

```css
div {
  position: relative;
  top: 10px;
  left: 20px;
}
```

### `z-index`

Controla a ordem de empilhamento no eixo Z.

#### **css**

```css
div {
  position: relative;
  z-index: 2;
}
```

---

### `absolute`

O elemento é removido do fluxo normal e posicionado em relação ao ancestral posicionado mais próximo.

#### **css**

```css
div {
  position: absolute;
  top: 0;
  left: 0;
}
```

---

### `fixed`

O elemento fica fixo em relação à janela do navegador, mesmo durante a rolagem.

#### **css**

```css
div {
  position: fixed;
  bottom: 10px;
  right: 10px;
}
```

---

### `sticky`

O elemento alterna entre `relative` e `fixed` conforme a rolagem da página.

#### **css**

```css
div {
  position: sticky;
  top: 0;
}
```

---

## `opacity`

Define o nível de transparência de um elemento.

- `1` = totalmente visível
- `0` = totalmente invisível

#### **css**

```css
div {
  opacity: 0.5;
}
```
## `overflow`

 controla o comportamento do conteúdo que ultrapassa as dimensões de seu contêiner (transborda), permitindo ocultar, mostrar ou adicionar barras de rolagem.

 - `visible` =  conteúdo transborda e fica visível fora da caixa do elemento.
 - `scroll` = O conteúdo excedente é cortado, mas barras de rolagem são adicionadas para permitir a visualização.
 - `auto` = Semelhante a ``scroll``, mas as barras de rolagem aparecem apenas quando o conteúdo realmente ultrapassa o limite.
 - `hidden` = O conteúdo que excede o limite é cortado e fica invisível.

    - ``overflow-x`` e ``overflow-y`` = Determinam o comportamento do transbordo especificamente na horizontal ou vertical, respectivamente.

    - ``text-overflow`` = Gerencia como o texto que transborda é exibido (ex: com reticências ...).

- A propriedade ``overflow`` também pode ser usada para conter elementos flutuantes, atuando como um "limpador" (``clearfix``) de layout. 

#### **css**

```css
.conteiner {
  width: 200px;
  height: 100px;
  overflow: auto; /* Adiciona rolagem apenas se necessário */
}
```

## `Float`

 é usada para posicionamento e formatação de conteúdo, permitindo que um elemento seja "flutuado" para a esquerda ou para a direita dentro de seu contêiner, forçando o texto e os elementos em linha (``inline``) a envolverem o elemento flutuante.

- ``left`` = O elemento flutua para a esquerda de seu contêiner. O texto e os elementos inline fluem ao redor do lado direito.
- ``right`` = O elemento flutua para a direita de seu contêiner. O texto e os elementos inline fluem ao redor do lado esquerdo.
- ``none`` (Padrão) = O elemento não flutua. Ele aparece na ordem normal do documento.
- ``inline-start`` = Flutua o elemento para o início da linha (esquerda em idiomas da esquerda para a direita, como o português).
- ``inline-end`` = Flutua o elemento para o final da linha (direita em idiomas da esquerda para a direita).
inherit = O elemento herda o valor float do seu elemento pai.

#### **css**

```css
img {
  float: left; /* A imagem flutua para a esquerda */
  margin-right: 15px; /* Adiciona espaço entre a imagem e o texto */
}

```
```css
img {
  float: left; /* A imagem flutua para a esquerda */
  margin-right: 15px; /* Adiciona espaço entre a imagem e o texto */
}

```

## `Dropdown`

Um efeito de menu dropdown (suspenso) em CSS é criado escondendo elementos com ``display: none`` e exibindo-os com ``display: block`` ao passar o mouse (:hover). A estrutura utiliza p``osition: relative`` no contêiner principal e ``position: absolute`` no conteúdo suspenso para posicioná-lo corretamente abaixo do item. 

### **css**

```css
/* Container que engloba o botão e o conteúdo */
.dropdown {
  position: relative;
  display: inline-block;
}

/* Conteúdo do dropdown (escondido) */
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

/* Mostra o dropdown ao passar o mouse */
.dropdown:hover .dropdown-content {
  display: block;
}

```