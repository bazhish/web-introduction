# Guia de HTML

## 1. Estrutura Básica

### Atributo `lang`
Define o idioma da página.
```html
<html lang="pt-BR">
```

---

## 2. Tag `<head>`

Contém metadados e configurações da página.  
Não é exibido diretamente ao usuário.

---

## 3. Metatags (`<meta>`)

Fornecem informações para navegadores e mecanismos de busca.

### Principais atributos:
- `charset` → define o conjunto de caracteres (ex: UTF-8)
- `viewport` → controla responsividade
- `description` → descrição da página (SEO)
- `keywords` → palavras-chave (menos relevante atualmente)
- `author` → autor da página

Exemplo:
```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

---

## 4. Cabeçalhos (`<h1>` a `<h6>`)

- `<h1>` → título principal (usar apenas um por página)
- `<h2>` a `<h6>` → subtítulos hierárquicos

Boa prática: manter estrutura semântica organizada.

---

## 5. SEO (Search Engine Optimization)

Conjunto de técnicas para melhorar o ranqueamento em buscadores:
- Uso correto de headings
- Meta description
- Conteúdo relevante
- HTML semântico

---

## 6. Formatação de Texto

### Semânticas (recomendadas)
- `<strong>` → importância (negrito)
- `<em>` → ênfase (itálico)

### Visuais (evitar para significado)
- `<b>` → negrito visual
- `<i>` → itálico visual

### Outras:
- `<mark>` → destaque
- `<small>` → texto menor
- `<del>` → removido
- `<ins>` → inserido
- `<sub>` → subscrito
- `<sup>` → sobrescrito
- `<hr>` → linha divisória
- `<u>` → sublinhado

---

## 7. Elementos de Citação

- `<abbr>` → abreviação (com `title`)
- `<address>` → endereço/contato
- `<cite>` → título de obra
- `<q>` → citação curta
- `<blockquote>` → citação longa
- `<bdo>` → inverter direção do texto

---

## 8. Comentários

Não são renderizados no navegador.

```html
<!-- Comentário -->
```

Atalho comum: `Ctrl + K + C`

---

## 9. Links (`<a>`)

Utilizados para navegação.

### Tipos:
- Absoluto → URL completa
- Relativo → dentro do projeto

### Atributos:
- `href` → destino
- `target="_blank"` → abre em nova aba

Exemplo:
```html
<a href="https://google.com" target="_blank">Ir para o Google</a>
```

---

## 10. Imagens (`<img>`)

Exibe imagens na página.

### Atributos:
- `src` → caminho da imagem
- `alt` → descrição (acessibilidade)
- `width` → largura
- `height` → altura

Exemplo:
```html
<img src="imagem.jpg" alt="Descrição da imagem">
```

### Observações:
- Para imagem ser link: envolver com `<a>`
- Bancos gratuitos: Pexels

---

## 11. Tabelas

### Estrutura:
- `<table>` → tabela
- `<tr>` → linha
- `<th>` → cabeçalho
- `<td>` → célula

Exemplo:
```html
<table>
  <tr>
    <th>Nome</th>
    <th>Idade</th>
  </tr>
  <tr>
    <td>Max</td>
    <td>17</td>
  </tr>
</table>
```

---

## 12. Listas

### Não ordenadas:
```html
<ul>
  <li>Item</li>
</ul>
```

### Ordenadas:
```html
<ol>
  <li>Item</li>
</ol>
```

---

## 13. Iframes

Permitem incorporar conteúdos externos.

Exemplo:
```html
<iframe src="https://example.com" width="600" height="400"></iframe>
```

Uso comum:
- Vídeos (YouTube)
- Páginas externas

---
## 14. Formulários

Formulários são usados para capturar dados do usuário.  
A tag é `<form>`

Exemplo básico:
```html
<form action="/enviar" method="post">
  <label for="nome">Nome:</label>
  <input type="text" id="nome" name="nome" placeholder="Digite seu nome" required>

  <button type="submit">Enviar</button>
</form>
```

### Atributos importantes da tag `<form>`
- `action`: define para onde os dados serão enviados
- `method`: define o método de envio, normalmente `get` ou `post`

### Tags comuns dentro de formulários

#### `<input>`
Cria campos de entrada de dados. O tipo é definido pelo atributo `type`.

Atributos importantes:
- `type`: define o tipo do campo
- `placeholder`: exibe um texto de orientação
- `id`: identifica o campo
- `name`: nome usado no envio do formulário
- `value`: valor do campo
- `required`: torna o preenchimento obrigatório

Tipos comuns:
- `text`: texto simples
- `password`: oculta o conteúdo digitado
- `email`: valida o formato básico de e-mail
- `radio`: seleção única
- `checkbox`: múltipla escolha
- `submit`: envia o formulário

Exemplo:
```html
<label for="email">E-mail:</label>
<input type="email" id="email" name="email" placeholder="Digite seu e-mail" required>
```

#### `<label>`
Cria uma legenda para o campo. O atributo `for` deve apontar para o `id` do input correspondente.

Exemplo:
```html
<label for="senha">Senha:</label>
<input type="password" id="senha" name="senha">
```

#### `placeholder`
O atributo placeholder no HTML fornece uma dica curta (exemplo ou descrição) dentro de campos `<input>` ou `<textarea>` antes de o usuário digitar algo. Ele melhora a usabilidade, guiando o preenchimento, e desaparece automaticamente ao focar e digitar no campo.

#### `radio`
Usado quando o usuário deve escolher apenas uma opção entre várias.

Regras importantes:
- todos os radios da mesma pergunta devem ter o mesmo `name`
- cada opção deve ter um `value`
- o `label` melhora acessibilidade e usabilidade

Exemplo:
```html
<p>Turno:</p>

<input type="radio" id="manha" name="turno" value="manha">
<label for="manha">Manhã</label>

<input type="radio" id="tarde" name="turno" value="tarde">
<label for="tarde">Tarde</label>
```

#### `checkbox`
Usado quando o usuário pode marcar mais de uma opção.

Exemplo:
```html
<input type="checkbox" id="html" name="tecnologia_html" value="html">
<label for="html">HTML</label>

<input type="checkbox" id="css" name="tecnologia_css" value="css">
<label for="css">CSS</label>
```

### Tag `<select>`
Cria uma lista suspensa para seleção de opções.

Exemplo:
```html
<label for="cidade">Cidade:</label>
<select id="cidade" name="cidade">
  <option value="" selected disabled>Selecione uma cidade</option>
  <option value="sp">São Paulo</option>
  <option value="rj">Rio de Janeiro</option>
</select>
```

#### Tags dentro de `<select>`
- `<option>`: representa cada opção
- `value`: valor enviado pelo formulário

Observação:
- `selected` marca uma opção inicialmente
- `disabled` desabilita a opção
- o correto é `selected disabled`, não `selected disable`

### Tag `<textarea>`
Cria uma caixa de texto para conteúdos longos.

Atributos comuns:
- `rows`: número de linhas visíveis
- `cols`: largura em colunas

Observação:
- também pode ser redimensionada com CSS usando a propriedade `resize`

Exemplo:
```html
<label for="mensagem">Mensagem:</label>
<textarea id="mensagem" name="mensagem" rows="5" cols="30"></textarea>
```

### Tag `<button>`
Cria um botão clicável.

Tipos mais comuns:
- `type="submit"`: envia o formulário
- `type="button"`: botão genérico
- `type="reset"`: limpa os campos

Exemplo:
```html
<button type="submit">Enviar</button>
<button type="reset">Limpar</button>
```

### Boas práticas em formulários
- usar `<label>` associado ao campo
- preencher `name` em todos os campos que serão enviados
- usar `required` apenas quando necessário
- escolher o `type` correto para melhorar validação e usabilidade
- priorizar acessibilidade e clareza
- `&nbsp;` cia um espaço vazio

---


## 15. Áudio

A tag `<audio>` é usada para incorporar arquivos de áudio em uma página HTML.

Normalmente, usa-se a tag filha `<source>` para informar o arquivo e seu tipo.

### Exemplo
```html
<audio controls controlsList="nodownload">
  <source src="audio/musica.mp3" type="audio/mpeg">
  Seu navegador não suporta áudio em HTML.
</audio>
```

### Estrutura
- `<audio>`: elemento principal de áudio
- `<source>`: informa o caminho do arquivo e o tipo de mídia

### Atributos importantes
- `src`: caminho do arquivo de áudio ou URL
- `type`: tipo do arquivo, como `audio/mpeg` ou `audio/ogg`
- `controls`: exibe os controles de reprodução
- `controlsList`: restringe algumas opções dos controles, como download

### Observações
- `controls` é necessário para o usuário visualizar os botões de reprodução
- `controlsList="nodownload"` pode ocultar a opção de download em navegadores compatíveis
- é recomendado adicionar um texto alternativo entre as tags para navegadores antigos

---

## 16. Vídeo

A tag `<video>` é usada para incorporar vídeos em uma página HTML.

Assim como no áudio, a tag `<source>` pode ser usada para indicar o arquivo e seu formato.

### Exemplo
```html
<video controls controlsList="nodownload" width="640" height="360" poster="imagens/capa.jpg" disablePictureInPicture>
  <source src="videos/apresentacao.mp4" type="video/mp4">
  Seu navegador não suporta vídeo em HTML.
</video>
```

### Estrutura
- `<video>`: elemento principal de vídeo
- `<source>`: informa o caminho do arquivo e o tipo de mídia

### Atributos importantes
- `src`: caminho do vídeo ou URL
- `type`: tipo do arquivo, como `video/mp4` ou `video/webm`
- `controls`: exibe os controles do vídeo
- `controlsList`: restringe algumas opções, como download
- `width`: largura do vídeo
- `height`: altura do vídeo
- `poster`: imagem de capa exibida antes da reprodução
- `autoplay`: faz o vídeo iniciar automaticamente
- `disablePictureInPicture`: remove a opção de mini player, quando suportado

### Observações importantes
- `width` e `height` definem o tamanho visível do vídeo
- `poster` funciona como uma thumbnail
- `autoplay` pode não funcionar sozinho em todos os navegadores, especialmente se o vídeo tiver som
- `disablePictureInPicture` depende do suporte do navegador

---

## `DIV`e HTML semântico

A tag `<div>` (divisão) no HTML é um contêiner genérico de nível de bloco, usado para agrupar elementos, estruturar layouts e aplicar estilos CSS ou scripts. Ela não possui significado semântico, sendo ideal para organização

A tag HTML `<header>` representa o cabeçalho de uma página ou seção, contendo conteúdo introdutório, logotipos, menus de navegação ou formulários de pesquisa.

A tag HTML `<nav>` define uma seção de links de navegação, sendo fundamental para a semântica, acessibilidade (leitores de tela) e SEO do site. Ela é destinada a blocos principais de navegação, como menus principais ou sumários, e não deve conter todos os links da página.

A tag ``<footer>`` no HTML define o rodapé de um site, seção ou artigo, contendo informações como direitos autorais, links de navegação, contatos ou autoria. Geralmente posicionado no final do ``<body>``, é um elemento semântico que melhora a estrutura e acessibilidade.

A tag ``<section>`` serve para agrupar conteúdos relacionados tematicamente, dividindo uma página em blocos lógicos ou macroestruturas (como introdução, notícias, contatos). Ela melhora a semântica, ajudando motores de busca (SEO) e leitores de tela a entenderem a hierarquia do documento, geralmente exigindo um título (`<h1>`-`<h6>`).

A tag ``<article>`` no HTML5 serve para definir conteúdo autônomo, independente e reutilizável dentro de uma página, como posts de blog, notícias, cards de produtos ou comentários. Ela é uma tag semântica que melhora o SEO, indicando aos motores de busca o conteúdo principal, e auxilia a acessibilidade para leitores de tela