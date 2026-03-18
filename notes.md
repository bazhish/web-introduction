# Guia Profissional de HTML (Resumo Organizado)

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