---
marp: true
theme: gaia
_class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.jpg')
---

# **PET Full Stack**

Aula 1

---

# Índice

- Objetivos
- Ambiente de desenvolvimento
- Overview das linguagens HTML, CSS e JavaScript
- HTML
- CSS
- JavaScript
- Sistemas Web

---

# Objetivos

Desenvolvimento web

- Como funciona e conceitos básicos
- Como escrever um _website_ bem simples
- Como pesquisar informação na _internet_

---

# Ambiente de desenvolvimento

- Navegador interpreta tudo, não precisa instalar nada
- Recomendado possuir um editor de código.
- É possível abrir arquivos HTML pelo navegador.
- Ferramentas de desenvolvedor (DevTools)

---

# Overview das linguagens

- HTML é o esqueleto da página
- CSS é a estilização da página, deixar o _site_ bonito
- JavaScript é a programação, e altera o comportamento padrão da página

---

# HTML

- Novas _features_ com HTML5
- Serve para gerar a árvore DOM
- Estrutura básica: html, head e body
- _Tags_ possuem o seguinte padrão:

```html
<tag attr1="val1" attr2="val2">...</tag>
```

---

# HTML

Para escrever um bom código, pense em:

- Elementos
- Hierarquia
- Layout
- Semântica

---

# CSS

- Estilizar, deixar o _site_ bonito
- Pode ser escrito:
  - direto no elemento
  - dentro de uma _tag_ style
  - dentro de um arquivo .css referenciado pela _tag_ link

---

# CSS

- _Rules_ possuem o seguinte padrão:

```css
seletor {
  propriedade1: valor1;
  propriedade2: valor2;
  ...;
}
```

---

# CSS

- Podemos selecionar elementos por
  - id
  - class
  - tipo de elemento
- Utilizamos DevTools -> Elements

---

# JavaScript

- Escrever na _tag_ script
- Mesmo recursos de outras linguagens
- Lidando com assincronismo
- Acessando DOM
- Utilizamos DevTools -> Console

---

# Sistemas Web

- Servidor com modelo _request_/_response_
- Protocolo HTTP
- Sistema de rotas
- Utilizamos DevTools -> Network e Sources
