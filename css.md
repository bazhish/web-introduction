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

- `color` = define a cor do texto e das decorações de um elemento HTML.
- `background` = usada para definir múltiplos estilos de plano de fundo em uma única linha, incluindo cor(`color`), imagem(`image`), posição(`position`), repetição(`repeat`), tamanho(`size`) e fixação.
- `border` =  usada é um atalho para definir a espessura, o estilo e a cor da borda ao redor de um elemento, posicionada entre o padding e a margin. A sintaxe abreviada border: `[width] [style] [color]`.

    - variação de bordas(`style`): `dashed`, `doted`, `solid`, `double`, ``groove``, ``ridge``, ``inset``, ``outset``, ``hiden``, ``none``
    - Há como mudar a posição da borda com: ``top``, ``left``, ``right``, ``bottom``
    - Para arredondar os cantos das bordas usamos `radius`

- `margin` =  define o espaçamento externo ao redor de um elemento, criando um espaço transparente fora de suas bordas para separá-lo de outros elementos. Ela pode ser aplicada a todos os lados de uma vez (``margin: 10px``) ou individualmente (``margin-top``, ``margin-right``, etc.), aceitando valores em ``px``, ``em``, ``%``, ``auto`` (para centralizar) ou valores negativos.

- `padding` = define o espaçamento interno, criando espaço entre o conteúdo de um elemento e suas bordas. Essencial no modelo de caixa, ela pode ter de um a quatro valores (``top``, ``right``, ``bottom``, ``left``) e aceita medidas fixas (``px``) ou relativas (``%``, ``em``, ``rem``). O ``padding`` não inclui a margem externa.
- `width` e `heigth` = As propriedades ``width`` (largura) e ``height`` (altura) no CSS definem as dimensões da área de conteúdo de um elemento HTML.
    - `max` = As propriedades ``max-width`` e ``max-height`` definem os limites máximos de largura e altura de um elemento, impedindo que ele cresça além de um valor específico, mesmo que seu conteúdo ou o valor de ``width``/``height`` sejam maiores.

- `text-align` = A propriedade ``text-align`` no CSS define o alinhamento horizontal de textos e elementos inline (como imagens ou links) dentro de um elemento de bloco (como ``<div>``, ``<p>``, ou ``<h1>``). Ela não afeta o alinhamento do bloco em si, apenas seu conteúdo interno. Os valores principais são ``left``, ``right``, ``center`` e ``justify``.

- `direction` = A propriedade ``direction`` no CSS define a direção do fluxo de texto, colunas de tabela e elementos inline (da esquerda para a direita - ``ltr``, ou direita para a esquerda - ``rtl``). É essencial para suporte a idiomas como árabe ou hebraico, influenciando o alinhamento padrão e a direção de escrita.

- `text-decoration` = A propriedade ``text-decoration`` no CSS é usada para adicionar linhas decorativas ao texto, como sublinhados (``underline``), linhas superiores (``overline``), tachado (``line-through``) ou remover decorações existentes (``none``). Ela é uma abreviação para definir cor, estilo e espessura da linha.

- `text-transformer` =  controla a capitalização (maiúsculas/minúsculas) de textos, permitindo alterar a aparência do texto sem modificar o HTML original. Os principais valores são: ``uppercase`` (tudo maiúsculo), ``lowercase`` (tudo minúsculo), ``capitalize`` (primeira letra de cada palavra em maiúsculo) e ``none`` (valor padrão, sem alterações). `spacing`(da um espaçmento entre as letras) 

- `line-height` = espaçamento entre as linhas
_ `world-spacing` = espaçamento entre as palavras
