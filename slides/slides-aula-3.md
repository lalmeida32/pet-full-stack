---
marp: true
theme: gaia
_class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.jpg')
---

# **PET Full Stack**

Aula 3

---

# Índice

- Objetivos
- Sistemas Web
- Node.js
- NPM
- Express

---

# Objetivos

Back-end de sistema web

- Aprofundamento em servidores HTTP
- Como criar um servidor utilizando Node.js
- Como hospedar o servidor no Heroku

---

# Sistemas Web

- Revisão de servidores HTTP
- Disponibilidade de outros recursos
  - arquivos
  - imagens
  - JSON

---

# Node.js

- Programa C++
- Ambiente de execução JavaScript fora do navegador
- Fornece outros tipos de API
- Utilizado para:
  - criação de programas CLI
  - criação de servidores

---

# NPM

- Gerenciador de pacotes Node.js
- Baixar bibliotecas de terceiros
- `package.json`, `package-lock.json`, `node_modules`
- Importar módulos via "require" (CommonJS)

---

# Express

- Criação de servidores HTTP facilitada
- Definir rotas e tipo de requisição
- Criação de um servidor que entrega páginas estáticas

```javascript
app.use('/', express.static('public'))
```
