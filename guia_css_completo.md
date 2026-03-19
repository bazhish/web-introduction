# Guia completo de CSS — do 0 ao avançado

## O que é CSS?

CSS (**Cascading Style Sheets**) é a linguagem usada para **estilizar** páginas web.
Enquanto o **HTML** organiza a estrutura do conteúdo, o **CSS** define a aparência: cores, tamanhos, espaçamentos, alinhamentos, animações, responsividade e layout.

### Exemplo simples

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

---

# 1. Como usar CSS

## CSS inline

Aplicado diretamente no elemento HTML.

```html
<p style="color: red;">Texto vermelho</p>
```

### Vantagem
- rápido para teste

### Desvantagem
- difícil de manter
- mistura estrutura com estilo
- não é profissional para projetos maiores

---

## CSS interno

Escrito dentro da tag `<style>` no `<head>` do HTML.

```html
<head>
  <style>
    p {
      color: green;
    }
  </style>
</head>
```

---

## CSS externo

Forma mais usada e recomendada.

```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

Arquivo `style.css`:

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

---

# 2. Sintaxe do CSS

```css
seletor {
  propriedade: valor;
}
```

### Exemplo

```css
h1 {
  color: black;
  font-size: 32px;
  text-align: center;
}
```

---

# 3. Seletores

## Seletor por elemento

```css
p {
  color: blue;
}
```

Seleciona todas as tags `<p>`.

---

## Seletor por id

```css
#titulo {
  color: red;
}
```

```html
<h1 id="titulo">Meu título</h1>
```

### Observação
- `id` deve ser único na página

---

## Seletor por classe

```css
.caixa {
  background: gray;
}
```

```html
<div class="caixa"></div>
```

### Observação
- classes podem ser reutilizadas em vários elementos

---

## Seletor universal

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

Seleciona todos os elementos.

Muito usado em reset inicial.

---

## Seletor de grupo

```css
h1, h2, p {
  font-family: Arial, sans-serif;
}
```

Aplica o mesmo estilo para vários elementos.

---

## Seletor descendente

```css
div p {
  color: green;
}
```

Seleciona todo `<p>` que estiver dentro de uma `<div>`.

---

## Seletor filho direto

```css
div > p {
  color: orange;
}
```

Seleciona apenas o filho direto.

---

## Seletor de irmão adjacente

```css
h1 + p {
  color: purple;
}
```

Seleciona o primeiro `<p>` logo após um `<h1>`.

---

## Seletor de irmãos gerais

```css
h1 ~ p {
  color: brown;
}
```

Seleciona todos os `<p>` irmãos após um `<h1>`.

---

## Seletor por atributo

```css
input[type="text"] {
  border: 1px solid black;
}
```

---

# 4. Cores e unidades

## Cores

### Nome da cor

```css
color: red;
```

### Hexadecimal

```css
color: #ff0000;
```

### RGB

```css
color: rgb(255, 0, 0);
```

### RGBA

```css
color: rgba(255, 0, 0, 0.5);
```

### HSL

```css
color: hsl(0, 100%, 50%);
```

---

## Unidades

### Absolutas
- `px`
- `cm`
- `mm`
- `in`
- `pt`

### Relativas
- `%`
- `em`
- `rem`
- `vw`
- `vh`
- `vmin`
- `vmax`
- `ch`

### Mais úteis no dia a dia
- `px` → tamanho fixo
- `%` → relativo ao elemento pai
- `rem` → relativo ao tamanho da fonte raiz
- `em` → relativo ao elemento atual
- `vw` e `vh` → relativo à tela

---

# 5. Texto e fontes

## color

```css
p {
  color: #333;
}
```

## font-size

```css
p {
  font-size: 16px;
}
```

## font-family

```css
body {
  font-family: Arial, sans-serif;
}
```

## font-weight

```css
h1 {
  font-weight: bold;
}
```

Valores comuns:
- `normal`
- `bold`
- `100` até `900`

## font-style

```css
p {
  font-style: italic;
}
```

## text-align

```css
h1 {
  text-align: center;
}
```

## text-decoration

```css
a {
  text-decoration: none;
}
```

## text-transform

```css
h2 {
  text-transform: uppercase;
}
```

## line-height

```css
p {
  line-height: 1.6;
}
```

## letter-spacing

```css
h1 {
  letter-spacing: 2px;
}
```

## word-spacing

```css
p {
  word-spacing: 4px;
}
```

## text-shadow

```css
h1 {
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}
```

---

# 6. Fundo

## background-color

```css
body {
  background-color: #f5f5f5;
}
```

## background-image

```css
body {
  background-image: url("fundo.jpg");
}
```

## background-repeat

```css
background-repeat: no-repeat;
```

## background-size

```css
background-size: cover;
```

## background-position

```css
background-position: center;
```

## shorthand background

```css
body {
  background: #000 url("fundo.jpg") no-repeat center/cover;
}
```

---

# 7. Box Model

Todo elemento HTML pode ser entendido como uma caixa.

O **Box Model** é formado por:
- conteúdo
- `padding`
- `border`
- `margin`

## width e height

```css
div {
  width: 300px;
  height: 150px;
}
```

## padding

Espaço interno.

```css
div {
  padding: 20px;
}
```

## border

```css
div {
  border: 2px solid black;
}
```

## margin

Espaço externo.

```css
div {
  margin: 20px;
}
```

## box-sizing

```css
* {
  box-sizing: border-box;
}
```

### Importância
Faz largura e altura incluírem padding e border no cálculo.

---

# 8. Bordas e sombras

## border-radius

```css
button {
  border-radius: 8px;
}
```

## box-shadow

```css
.card {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}
```

## outline

```css
input {
  outline: 2px solid blue;
}
```

---

# 9. Display

## block
Ocupa a largura inteira.

Exemplos: `div`, `p`, `h1`

## inline
Ocupa apenas o tamanho do conteúdo.

Exemplos: `span`, `a`, `strong`

## inline-block
Mistura comportamento inline com controle de largura e altura.

```css
span {
  display: inline-block;
}
```

## none
Remove o elemento visualmente.

```css
.menu {
  display: none;
}
```

---

# 10. Position

## static
Padrão.

## relative
Permite deslocar o elemento mantendo seu espaço original.

```css
.caixa {
  position: relative;
  top: 10px;
  left: 20px;
}
```

## absolute
Posicionado em relação ao ancestral posicionado mais próximo.

```css
.filho {
  position: absolute;
  top: 0;
  right: 0;
}
```

## fixed
Fica preso na tela.

```css
.topo {
  position: fixed;
  top: 0;
  width: 100%;
}
```

## sticky
Gruda ao rolar quando atinge certa posição.

```css
.menu {
  position: sticky;
  top: 0;
}
```

## z-index
Controla a ordem de sobreposição.

```css
.modal {
  position: fixed;
  z-index: 999;
}
```

---

# 11. Overflow

```css
.caixa {
  overflow: hidden;
}
```

Valores comuns:
- `visible`
- `hidden`
- `scroll`
- `auto`

---

# 12. Flexbox

Usado para alinhar e distribuir elementos em uma dimensão.

## Container flex

```css
.container {
  display: flex;
}
```

## Direção

```css
flex-direction: row;
flex-direction: column;
```

## Alinhamento no eixo principal

```css
justify-content: center;
```

Valores comuns:
- `flex-start`
- `center`
- `flex-end`
- `space-between`
- `space-around`
- `space-evenly`

## Alinhamento no eixo cruzado

```css
align-items: center;
```

## Quebra de linha

```css
flex-wrap: wrap;
```

## Espaçamento

```css
gap: 16px;
```

## Propriedades dos filhos

```css
.item {
  flex: 1;
}
```

```css
.item {
  align-self: center;
}
```

### Exemplo

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
}
```

---

# 13. Grid Layout

Usado para criar layouts bidimensionais.

## Container grid

```css
.container {
  display: grid;
}
```

## Colunas

```css
grid-template-columns: 1fr 1fr 1fr;
```

## Linhas

```css
grid-template-rows: auto auto;
```

## Espaçamento

```css
gap: 20px;
```

## Recurso muito usado

```css
grid-template-columns: repeat(3, 1fr);
```

## Layout responsivo automático

```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

## Posicionar item

```css
.item {
  grid-column: 1 / 3;
  grid-row: 1 / 2;
}
```

---

# 14. Pseudo-classes

Mudam o estilo de acordo com estado ou posição.

## hover

```css
button:hover {
  background: blue;
}
```

## focus

```css
input:focus {
  outline: 2px solid green;
}
```

## active

```css
button:active {
  transform: scale(0.98);
}
```

## visited

```css
a:visited {
  color: purple;
}
```

## first-child

```css
li:first-child {
  color: red;
}
```

## last-child

```css
li:last-child {
  color: blue;
}
```

## nth-child

```css
li:nth-child(2) {
  color: orange;
}
```

## not

```css
p:not(.especial) {
  color: gray;
}
```

---

# 15. Pseudo-elementos

## before

```css
h1::before {
  content: "★ ";
}
```

## after

```css
h1::after {
  content: " ✓";
}
```

## placeholder

```css
input::placeholder {
  color: gray;
}
```

## selection

```css
::selection {
  background: yellow;
}
```

---

# 16. Transições

Permitem animações suaves entre estados.

```css
button {
  transition: background 0.3s ease, transform 0.3s ease;
}

button:hover {
  background: black;
  transform: translateY(-2px);
}
```

### Partes do `transition`
- propriedade
- duração
- timing function
- delay (opcional)

---

# 17. Transformações

## translate

```css
transform: translateX(20px);
```

## scale

```css
transform: scale(1.1);
```

## rotate

```css
transform: rotate(45deg);
```

## skew

```css
transform: skew(10deg, 5deg);
```

---

# 18. Animações

## Criando uma animação

```css
@keyframes aparecer {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
```

## Aplicando

```css
.caixa {
  animation: aparecer 1s ease-in-out;
}
```

### Propriedades úteis
- `animation-name`
- `animation-duration`
- `animation-timing-function`
- `animation-delay`
- `animation-iteration-count`
- `animation-direction`
- `animation-fill-mode`

### Exemplo completo

```css
.loader {
  animation: girar 1s linear infinite;
}

@keyframes girar {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
```

---

# 19. Responsividade

Responsividade é adaptar o layout para diferentes tamanhos de tela.

## Imagens fluidas

```css
img {
  max-width: 100%;
  height: auto;
}
```

## Unidades relativas
Use mais:
- `%`
- `rem`
- `vw`
- `fr`
- `minmax()`

## Media Queries

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

### Breakpoints comuns
- `480px` → celulares menores
- `768px` → tablet / celular grande
- `1024px` → notebook
- `1200px` ou mais → desktop maior

---

# 20. Variáveis CSS

Também chamadas de **custom properties**.

```css
:root {
  --cor-primaria: #2563eb;
  --espacamento: 16px;
}

button {
  background: var(--cor-primaria);
  padding: var(--espacamento);
}
```

### Vantagens
- facilita manutenção
- melhora consistência visual
- ótima para temas

---

# 21. Herança e cascata

## Herança
Algumas propriedades passam do pai para o filho.

Exemplo:
- `color`
- `font-family`
- `line-height`

---

## Cascata
Quando mais de uma regra atinge o mesmo elemento, o navegador decide qual aplicar.

Critérios principais:
- importância (`!important`)
- especificidade
- ordem no arquivo

---

## Especificidade

Ordem simplificada:
1. seletor universal `*`
2. elemento `p`
3. classe `.classe`
4. atributo `[type="text"]`
5. pseudo-classe `:hover`
6. id `#id`
7. inline `style=""`
8. `!important`

### Exemplo

```css
p {
  color: blue;
}

.texto {
  color: green;
}

#mensagem {
  color: red;
}
```

Se o elemento tiver os três, vence o `#mensagem`.

---

# 22. Reset e Normalize

## Reset básico

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

### Objetivo
Reduzir diferenças de estilo padrão entre navegadores.

---

# 23. Boas práticas de organização

## Separar por seções

```css
/* Reset */
/* Layout */
/* Cabeçalho */
/* Conteúdo principal */
/* Rodapé */
/* Responsividade */
```

## Nomes claros
Use classes com nomes descritivos:

```css
.card-produto {}
.botao-primario {}
.menu-lateral {}
```

Evite nomes vagos:

```css
.caixa1 {}
.azulzinho {}
.coisa {}
```

## Evite excesso de especificidade
Prefira:

```css
.botao {}
```

ao invés de:

```css
body main section div .botao {}
```

## Reutilização
Crie classes reutilizáveis para:
- botões
- cards
- containers
- espaçamentos
- títulos

---

# 24. CSS para formulários

## Inputs

```css
input, textarea, select, button {
  font: inherit;
}
```

## Exemplo de input estilizado

```css
input {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 8px;
}

input:focus {
  outline: none;
  border-color: #2563eb;
  box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.2);
}
```

---

# 25. CSS para imagens e mídia

## object-fit

```css
img {
  width: 100%;
  height: 250px;
  object-fit: cover;
}
```

Valores comuns:
- `cover`
- `contain`
- `fill`
- `none`

---

# 26. Funções úteis do CSS

## calc()

```css
width: calc(100% - 40px);
```

## clamp()

Muito útil para responsividade.

```css
font-size: clamp(1rem, 2vw, 2rem);
```

## min() e max()

```css
width: min(100%, 1200px);
height: max(300px, 50vh);
```

---

# 27. Filtros e efeitos visuais

## filter

```css
img {
  filter: grayscale(100%);
}
```

Outros exemplos:
- `blur()`
- `brightness()`
- `contrast()`
- `drop-shadow()`

## backdrop-filter

```css
.card {
  backdrop-filter: blur(10px);
}
```

---

# 28. Scroll e comportamento

## scroll-behavior

```css
html {
  scroll-behavior: smooth;
}
```

## resize

```css
textarea {
  resize: vertical;
}
```

## cursor

```css
button {
  cursor: pointer;
}
```

---

# 29. Estados comuns de interface

## Desabilitado

```css
button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
```

## Erro em formulário

```css
.input-erro {
  border-color: red;
}
```

## Sucesso

```css
.sucesso {
  color: green;
}
```

---

# 30. Metodologias de nomenclatura

## BEM

BEM = **Block Element Modifier**

### Exemplo

```css
.card {}
.card__titulo {}
.card__texto {}
.card--destaque {}
```

### Vantagens
- clareza
- organização
- manutenção melhor
- muito usado em projetos grandes

---

# 31. Integração com HTML e JavaScript

O CSS quase sempre trabalha junto com HTML e JS.

### Exemplo: classe dinâmica

HTML:

```html
<button id="btn">Abrir menu</button>
<nav class="menu"></nav>
```

CSS:

```css
.menu {
  display: none;
}

.menu.ativo {
  display: block;
}
```

JavaScript:

```javascript
const menu = document.querySelector('.menu');
const btn = document.querySelector('#btn');

btn.addEventListener('click', () => {
  menu.classList.toggle('ativo');
});
```

---

# 32. Acessibilidade no CSS

CSS também impacta acessibilidade.

## Boas práticas
- mantenha contraste bom entre texto e fundo
- não remova foco sem substituir por outro estilo visível
- não use texto pequeno demais
- não dependa só de cor para indicar erro ou sucesso
- respeite leitura e espaçamento
- cuidado com animações excessivas

### Exemplo ruim

```css
input:focus {
  outline: none;
}
```

### Melhor

```css
input:focus {
  outline: 2px solid #2563eb;
  outline-offset: 2px;
}
```

---

# 33. Performance e manutenção

## Dicas importantes
- evite CSS repetido
- reaproveite classes
- use variáveis
- não exagere em sombras, filtros e animações pesadas
- prefira layouts simples e claros
- organize media queries
- mantenha nomes consistentes

---

# 34. Propriedades shorthand

Shorthand é forma resumida de escrever várias propriedades.

## margin

```css
margin: 10px 20px 30px 40px;
```

Ordem:
- topo
- direita
- baixo
- esquerda

## padding

```css
padding: 10px 20px;
```

## border

```css
border: 1px solid #000;
```

## font

```css
font: italic bold 16px/1.5 Arial, sans-serif;
```

## background

```css
background: #111 url("img.jpg") no-repeat center/cover;
```

---

# 35. Tópicos avançados que vale estudar depois

Depois de dominar a base, avance para:
- arquitetura CSS
- Sass / SCSS
- Tailwind CSS
- CSS Modules
- Styled Components
- animações complexas
- design systems
- container queries
- `:is()`, `:where()`, `:has()`
- `@supports`
- `@layer`
- modo escuro com variáveis

### Exemplo de `@supports`

```css
@supports (display: grid) {
  .layout {
    display: grid;
  }
}
```

### Exemplo de container queries

```css
.card-container {
  container-type: inline-size;
}

@container (max-width: 400px) {
  .card {
    font-size: 14px;
  }
}
```

---

# 36. Estrutura recomendada de um arquivo CSS profissional

```css
/* 1. Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* 2. Variáveis */
:root {
  --cor-primaria: #2563eb;
  --cor-texto: #222;
  --cor-fundo: #f8fafc;
  --radius: 12px;
}

/* 3. Base */
body {
  font-family: Arial, sans-serif;
  color: var(--cor-texto);
  background: var(--cor-fundo);
}

/* 4. Layout */
.container {
  width: min(100% - 32px, 1200px);
  margin-inline: auto;
}

/* 5. Componentes */
.botao {
  padding: 12px 20px;
  border: none;
  border-radius: var(--radius);
  background: var(--cor-primaria);
  color: white;
  cursor: pointer;
  transition: 0.3s ease;
}

.botao:hover {
  transform: translateY(-2px);
}

/* 6. Responsividade */
@media (max-width: 768px) {
  .container {
    width: min(100% - 20px, 1200px);
  }
}
```

---

# 37. O que você precisa dominar para saber CSS de verdade

## Base
- sintaxe
- seletores
- cores
- unidades
- texto e fontes
- box model
- display
- position

## Intermediário
- flexbox
- grid
- pseudo-classes
- pseudo-elementos
- transições
- transformações
- responsividade
- variáveis CSS

## Avançado
- cascata e especificidade
- organização de código
- acessibilidade visual
- performance
- efeitos modernos
- container queries
- design system
- arquitetura CSS

---

# 38. Erros comuns de iniciantes

- esquecer o `;`
- usar `id` demais em vez de classes
- não entender `margin` e `padding`
- não usar `box-sizing: border-box`
- tentar centralizar sem entender flexbox
- usar valores fixos demais
- ignorar responsividade
- remover `outline` do foco
- criar seletores muito longos
- repetir estilos desnecessariamente

---

# 39. Resumo rápido

CSS serve para estilizar páginas.

Você precisa dominar principalmente:
- seletores
- box model
- display
- position
- flexbox
- grid
- responsividade
- cascata e especificidade
- boas práticas

Se dominar isso bem, você já sai do básico e entra em um nível muito forte para projetos reais.

---

# 40. Mini exemplo completo

## HTML

```html
<div class="card">
  <h2 class="card__titulo">Produto</h2>
  <p class="card__texto">Descrição do produto.</p>
  <button class="botao">Comprar</button>
</div>
```

## CSS

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  min-height: 100vh;
  display: grid;
  place-items: center;
  font-family: Arial, sans-serif;
  background: #f5f5f5;
}

.card {
  width: 320px;
  padding: 24px;
  border-radius: 16px;
  background: white;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.12);
}

.card__titulo {
  margin-bottom: 12px;
  font-size: 24px;
}

.card__texto {
  margin-bottom: 20px;
  line-height: 1.5;
  color: #444;
}

.botao {
  padding: 12px 16px;
  border: none;
  border-radius: 10px;
  background: #2563eb;
  color: white;
  cursor: pointer;
  transition: 0.3s ease;
}

.botao:hover {
  transform: translateY(-2px);
}
```

---

# 41. Fechamento

Se HTML é a estrutura da casa, o CSS é o acabamento, a pintura, a organização visual e a forma como tudo fica bonito, legível e funcional.

Aprender CSS de verdade não é decorar propriedades. É entender:
- como os elementos ocupam espaço
- como o navegador calcula layout
- como construir interfaces limpas
- como tornar tudo responsivo e utilizável

Quando você dominar isso, seu nível sobe muito.
