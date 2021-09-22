# PET Full Stack - Notas de Aula



## Aula 3



### Índice

---

[Objetivos](#objetivos)

[Sistemas Web - Continuação](#sistemas-web)

[Node.js](#nodejs)

[NPM](#npm)

[Express](#express)

[Deploy](#deploy)

---



### Objetivos<a name="objetivos"></a>

---

Esta aula tem como objetivo familiarizar o aluno com um *back-end* simples, que entrega páginas estáticas ao cliente.

- aprofundamento em servidores HTTP;
- como criar um servidor utilizando Node.js;
- como hospedar o servidor no Heroku.

---



### Sistemas Web - Continuação<a name="sistemas-web"></a>

---



---



### Node.js<a name="nodejs"></a>

---

Node.js é um programa, escrito em C++, capaz de executar JavaScript fora do navegador e que fornece APIs para lidar com recursos do sistema operacional.

Todo navegador, para funcionar adequadamente, possui:

- Um motor JavaScript, que interpreta o código e permite a execução da lógica.
- Diversas APIs para lidar com o navegador, com a página e com o DOM.

O Node.js também possui um motor JavaScript dentro dele, no entanto, as APIs fornecidas são completamente diferentes.

Alguns exemplos de APIs fornecidas pelo navegador: `window`, `document`, `console`.

Alguns exemplos de APIs fornecidas pelo Node.js: `global`, `console`, `fs (file system)`, `http`, `os`, `path`.

Através do Node.js, conseguimos criar qualquer tipo de programa utilizando JavaScript, como por exemplo CLIs (programas de linha de comando) ou servidores *back-end*. Essas duas aplicações são as mais comuns quanto ao uso do Node.js.

---



### NPM<a name="npm"></a>

---

NPM é um gerenciador de pacotes Node.js. Através dele, é bem simples adicionar "bibliotecas" de terceiros em nosso código.

Para checar se o NPM está devidamente instalado e adicionado ao PATH do sistema operacional, execute o comando: `npm --version`.

Segue uma lista dos comandos mais comuns do NPM:

```bash
Criar arquivo de configuração package.json
npm init

Instalar pacote local (dentro de um projeto específico)
npm i <package_name>

Instalar pacote no computador (útil para programas do tipo CLI)
npm i -g <package_name>

Desinstalar pacote local
npm un <package_name>

Listar pacotes instalados
npm list --depth=0
```

**Observação:** Utilizar a *flag* `-g` fará referência a pacotes instalados globalmente.

**Observação 2:** Caso não seja especificada a versão do pacote utilizado, a versão estável mais recente será instalada.

Informações sobre os pacotes podem ser encontradas em https://www.npmjs.com/.

O NPM não é o único gerenciador de pacotes Node.js. Existe outro bem conhecido e amplamente utilizado chamado Yarn, e não há muita diferença entre os dois, pois em geral, os pacotes mais famosos estão presentes nas duas plataformas.

#### Criando um projeto simples

Crie um novo diretório, de preferência com um nome sem espaços e em letras minúsculas, e execute os seguintes comandos:

```bash
npm init -y
npm i express
```

O primeiro comando criará o arquivo de configuração `package.json` com informações padrão do projeto. Sinta-se livre para abrir o arquivo e alterá-lo da maneira que achar melhor.

Ao executar o segundo comando, três coisas acontecerão:

- Será criada um novo diretório chamado `node_modules`. Ele será responsável por conter não só os pacotes instalados localmente, mas a dependência dos pacotes instalados também. Pense que o Express, por exemplo, também é um programa em Node.js que precisa de outros pacotes para funcionar.
- Será criado um arquivo chamado `package-lock.json`, que serve para mapear as dependências entre os pacotes instalados. Este, assim como `package.json` é um arquivo de configuração, com a diferença de que nós, desenvolvedores, não mexemos nesse arquivo diretamente. Deixe para que os comandos `npm` façam isso.
- Será adicionada como dependência do nosso projeto o pacote Express. Verifique isso dentro do arquivo `package.json`.

Com isso, podemos criar um arquivo simples Node.js. Para importar o Express em nosso projeto, utilizaremos a função `require`, também disponibilizada por padrão no Node.js.

```js
const express = require('express')
```

A *string* passada como argumento da função é o nome do pacote instalado. O que a função `require` retorna depende do pacote instalado, sendo que no caso do Express é retornada uma função.

```js
const express = require('express')
const app = express()
```

Chamando essa função, obtemos um objeto que representará nosso programa. Isso será abordado com mais detalhes no próximo tópico.

---



### Express<a name="express"></a>

---

O Express é um pacote que facilita muito o desenvolvimento de servidores *back-end* que utilizam Node.js. Ele utiliza, por baixo dos panos, a API `http` fornecida por padrão pelo Node.js. 

---



### Deploy<a name="deploy"></a>

---



---

