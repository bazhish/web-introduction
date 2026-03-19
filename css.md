# Guia de CSS

## CSS inline

 O CSS Inline é uma das formas de aplicação, inserindo estilos diretamente em uma tag HTML via atributo style (ex: ``<p style="color: blue;">``), tendo a maior prioridade, mas sendo recomendado apenas para correções rápidas devido à dificuldade de manutenção.

## CSS Interno

O CSS interno é aplicado adicionando a tag ``<style>`` dentro da seção ``<head>`` de um arquivo HTML específico. Ele permite estilizar elementos da página atual sem arquivos externos, sendo ideal para páginas únicas ou testes rápidos, mas ineficiente para sites grandes devido à repetição de código.

## CSS Externo

O CSS externo é a prática para estilizar paginas, utilizando um arquivo separado com extensão .css vinculado ao HTML via tag ``<link rel = "stylesheet" href = "caminho do arquivo">`` no ``<head>``. Isso separa conteúdo de design, facilitando a manutenção e permitindo aplicar o mesmo estilo em várias páginas, garantindo consistência e carregamento rápido. 