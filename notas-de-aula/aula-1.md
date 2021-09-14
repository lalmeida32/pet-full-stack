# PET Full Stack - Notas de Aula





## Aula 1



### Objetivos

---

Esta aula tem como objetivo familiarizar o aluno com o básico do desenvolvimento web:

- como funciona e conceitos básicos;
- como escrever um *website* bem simples;
- como pesquisar informação na *internet*.

---



### Ambiente de desenvolvimento

---

Um *website* é construído em cima de três linguagens: HTML, CSS e JavaScript. Essas três serão melhor detalhadas no tópico seguinte, mas antes de mais nada é importante entender que **o navegador entende essas linguagens nativamente**. Ou seja, para desenvolver com essas linguagens basta possuir um navegador de *internet*.

#### Editores de código

Apesar de não ser necessário, é recomendado possuir instalado um editor de código, como:

- Visual Studio Code (não confundir com Visual Studio)
- Atom
- Sublime Text 
- Notepad++
- Vim

Para desenvolvimento *web*, é muito comum a utilização do editor Visual Studio Code por conta das ferramentas e extensões que ele provê, mas nesse começo de aprendizado muitos desses utensílios podem não fazer sentido e desviar o foco, então escolha o editor que estiver acostumado.

#### Abrindo arquivos HTML com o navegador

Crie, através do editor de código, um arquivo com extensão `.html` e insira o seguinte código:

```html
<html>
    <body><h1>Hello, world!</h1></body>
</html>
```

Abra o arquivo com seu navegador e preste atenção na URL. Perceba que ela começa com `file://` ao invés de `http://`, como é comum em páginas *web*. Esse é o *URL scheme*, e serve para identificar a "maneira" como o navegador está recebendo um recurso. Isso ficará mais claro no futuro, apenas entenda que há diferenças entre abrir um arquivo `.html` diretamente no navegador, e utilizar o protocolo HTTP.

O que aconteceu aqui foi que o navegador acessou o arquivo através da URL, recebeu os dados do arquivo, interpretou e exibiu `Hello, world!`, o que significa que de fato, o navegador é capaz de interpretar HTML nativamente.

No entanto, para interpretar código CSS ou JavaScript no navegador, é preciso colocá-lo "dentro" de um documento HTML. O arquivo HTML é o ponto de entrada de um *website*.

**Bônus:** Depois desta aula, tente abrir um arquivo `.js` diretamente pelo navegador e perceba que o código é apenas mostrado, mas não executado. Como foi dito, para que o navegador interprete código CSS ou JavaScript, é necessário que o código esteja "dentro" de um código HTML. No entanto, a maioria dos navegadores atuais são capazes de abrir diretamente outros tipos de arquivo, como imagens e PDFs. Com isso, é possível utilizar um navegador no lugar do visualizador de imagens padrão do sistema operacional, por exemplo.

#### DevTools

Praticamente todo navegador *web* provê "ferramentas de desenvolvedor" (também chamadas de DevTools). Essas ferramentas são extremamente úteis para *debug*, podendo ser utilizadas não somente para o código HTML, CSS e JavaScript, mas também para rede e segurança. Aos poucos, nesta aula, entenderemos como usar algumas dessas ferramentas.

---



### Overview das linguagens HTML, CSS e JavaScript

---

As três linguagens se completam no desenvolvimento de uma página *web*.

- HTML serve para definir o esqueleto da página. Nele definimos os elementos presentes e a hierarquia entre eles.
- CSS serve para definir a estilização dos elementos, "deixar o *site* bonito".
- JavaScript serve para programar, escrevendo algoritmos que alteram o comportamento padrão da página.

Vamos alterar o código anterior e colocar um pouco de código CSS.

```html
<html>
    <head>
        <style>
            h1 {
                color: red;
            }
        </style>
    </head>
    <body>
        <h1>Hello, world!</h1>
    </body>
</html>
```

**Observação:** O código dentro da *tag* `style` não é HTML, e sim CSS.

**Observação 2:** Indentações e espaços entre as *tags* (o que está entre os símbolos `<` e `>`) não influenciam no resultado da página.

Salve e atualize a página no navegador. Perceba que agora o texto `Hello, world!` está em vermelho. Apenas reforçando: código CSS serve para estilizar a página.

Vamos adicionar agora um botão e um código JavaScript para acrescentar comportamento ao botão.

```html
<html>
    <head>
        <style>
            h1 {
                color: red;
            }
        </style>
    </head>
    <body>
        <h1>Hello, world!</h1>
        <button id="botao">Clique em mim</button>
        <script> 
            var botao = document.getElementById("botao");
            botao.onclick = function() {
                alert("Clicado!");
            }
        </script>
    </body>
</html>
```

**Observação:** O código dentro da *tag* `script` não é HTML, e sim JavaScript.

**Observação 2:** Perceba que o código JavaScript precisou ser adicionado após a definição do botão. Caso contrário, não seria possível acessar esse elemento com `document.getElementById`. Perceba também que, com a *tag* `style`, não houve essa preocupação.

A ideia desse tópico era apresentar as três linguagens e assimilar a função de cada uma delas. Não se preocupe, cada linguagem será abordada com mais detalhes a partir de agora.

---



### HTML

---

Vamos falar brevemente sobre a linguagem HTML.

Antes de mais nada, vamos utilizar a versão com mais *features*, o HTML5. Para utilizar HTML5 no seu código, basta adicionar ao topo do arquivo, na primeira linha: `<!DOCTYPE html>`.

#### Função da linguagem

Como dito anteriormente, HTML é uma linguagem que serve para definir o esqueleto de uma página *web*. Mais detalhadamente, utilizamos a linguagem HTML para definir como será nosso DOM (Document Object Model).

O DOM é um modelo, em forma de árvore, que armazena todas as informações para renderizar uma página *web*. Cada nó dessa árvore é chamado de "DOM Element", e possui uma relação direta com as *tags* do HTML. O navegador interpreta o código HTML e converte cada *tag* em um elemento do DOM, por isso dizemos que a linguagem HTML é uma linguagem de **marcação**.

Cada elemento DOM possui vários atributos que podem ser alterados via JavaScript ou HTML. Já a linguagem CSS foi desenhada para manipular principalmente o atributo `style`.

#### Estrutura básica

Mesmo com um código HTML em branco, o navegador cria no DOM ao menos os elementos `html`, `head` e `body`. Isso pode ser verificado abrindo as DevTools e verificando os elementos da página. Esses elementos são a base de toda página *web*.

Segue a função dos elementos:

- `html`: É a raiz do DOM. Todos os outros elementos devem ser filhos deste.
- `head`: Deve possuir como filhos elementos que **não são renderizados**.
- `body`: Deve possuir como filhos elementos que **são renderizados**.

**Observação:** Nas DevTools é comum utilizar código HTML para descrever o DOM, afinal, facilita a leitura do desenvolvedor.

**Bônus:** No tópico anterior utilizamos a *tag* `script` dentro do `body`. Com as novas *features* do HTML5, é possível colocar a *tag* `script` no `head` e acrescentar o atributo `defer`. Esse atributo fará com que o código JavaScript seja executado após a construção do DOM.

#### *Tags* HTML

Como foi dito anteriormente, em geral cada *tag* HTML corresponde a um elemento DOM. O *website* https://allthetags.com/ possui informações sobre várias delas.

É possível que algumas *tags* não sejam suportadas por versões mais antigas do HTML e dos navegadores. Nesse caso, o *website* https://caniuse.com/ se mostra muito útil. Nele contém informação sobre quais navegadores suportam determinada *feature*, não só do HTML mas do CSS e do JavaScript também. Além disso, o *site* informa sobre quantas pessoas no mundo utilizam determinada versão de um navegador.

Em geral, a sintaxe de uma *tag* pode ser encontrada em uma das seguintes formas:

```html
<!-- Padrão -->
<nomeDoElemento atributo1="valor1" atributo2="valor2" atributoBooleano1 atributoBooleano2>
    Conteúdo interno (inner HTML)
    <tagInterna>...</tagInterna>
</nomeDoElemento>

<!-- Self closing -->
<nomeDoElemento atributo1="valor1" atributo2="valor2" atributoBooleano1 atributoBooleano2 />
```

Entre os símbolos `<>` deve ser informado primeiramente qual elemento será criado no DOM, como por exemplo, `p` para criar um parágrafo. Em seguida, informamos como os atributos padrão do elemento serão sobrescritos.

Sobre os atributos, é importante notar duas coisas:

- Elementos diferentes, em geral, possuem conjuntos de atributos diferentes. Na *tag* `img` (*image*), por exemplo, é comum utilizar o atributo `src` para definir o local em que aquela imagem pode ser encontrada. Esse atributo não faz sentido para a *tag* `p` (*paragraph*), que serve para lidar com texto.
- A maioria dos atributos podem receber uma "*string*" como valor, com exceção dos atributos booleanos. A presença deles indica *true*, e a ausência *false*, não se engane fazendo algo como `atributoBooleano="false"`. O navegador entenderá isso como *true*.

**Importante:** Grande parte das *tags* podem ser "abertas" (`<>`) e "fechadas" (`</>`). Esse tipo de *tag* pode possuir filhos na árvore de elementos DOM, e esses filhos devem ser colocados entre a abertura e o fechamento da *tag*. Nesse exemplo, o elemento referente à primeira *tag* possui como filhos um *text node* e um elemento do tipo `tagInterna`.  Enquanto isso, as *tags* do tipo *self closing* não possuem filhos.

**Observação:** O conteúdo dentro de `<!--` e `-->` é um comentário, ou seja, não será interpretado pelo navegador, mas ajuda a organizarmos o código.

#### Um pouco de prática

Dominar esses conceitos iniciais é importantíssimo para saber o que acontece por "baixo dos panos", evitando *bugs*, e  para saber como pesquisar e ler informação na internet.

No entanto, a prática é essencial, não apenas para fixar os conceitos aprendidos, mas também para se familiarizar com as *tags* e seus atributos.

Vamos criar um *tweet* simples utilizando HTML.

```html
<div>
    
    <header>
        <img src="img/neymar.jpg" />
        <h2>Neymar Jr</h2>
        <h3>@neymarjr</h3>
    </header>
    
    <p>
        Bora falar de bbb porque de futebol esse fds não foi legal 😢
    </p>
    
    <footer>
        <p>
            6:14 p. m. - 31 jan. 2021 - Twitter for iPhone
        </p>
    </footer>
    
</div>
```

Note que, como ainda não aprendemos CSS, não será possível estilizar o *tweet*. Foque, por enquanto, na estrutura básica.

Segue uma breve explicação de cada um dos elementos:

- `div`: Uma divisão no *layout*, serve para agrupar elementos relacionados (terá uma utilidade maior no CSS).
- `header` e `footer`: Mesma coisa que `div`, mas com um significado semântico. Facilita um pouco a leitura do código e o entendimento dos mecanismos de busca (Google, Bing, DuckDuckGo, etc) sobre a sua página.
- `img`: Imagem cujo atributo `src` contém o local em que ela pode ser encontrada.
- `h2` e `h3`: Hierarquia de títulos e subtítulos (juntamente com `h1`, `h4`, `h5` e `h6`)
- `p`: Trecho de texto, não necessariamente utilizado literalmente para parágrafos textuais.

**Observação:** Neste código estão sendo omitidas as *tags* `html` e `body`, mas elas devem estar presentes no seu código, bem como a indicação de uso do HTML5: `<!DOCTYPE html>`. 

**Observação 2:** É quase certo que este código HTML precisará ser alterado quando introduzirmos o CSS. 

#### Referência para recursos

Como foi visto no último código, podemos utilizar o atributo `src` da *tag* `img` para referenciar um arquivo do tipo imagem. Perceba que para que o código funcione adequadamente, a pasta `img` deve estar na mesma pasta que o nosso arquivo HTML, e deve existir dentro de `img` um arquivo de imagem chamado `neymar.jpg`.

Isso tudo porque **estamos utilizando o sistema de arquivos** para navegar entre os recursos. Nesse caso, `img/neymar.jpg` é equivalente a `./img/neymar.jpg`. Já se utilizarmos `/img/neymar.jpg`, teremos uma referência para a raiz do sistema de arquivos, seguida de uma pasta `img` e um arquivo de imagem.

Guarde este exemplo na memória. Ainda nesta aula, utilizaremos o protocolo HTTP e haverá grandes diferenças quanto a essas referências.

Apenas para fixar, vamos criar um novo arquivo HTML dentro da mesma pasta que o arquivo inicial, em `views/about.html`. Era comum em *websites* mais antigos, como *blogs*, a presença de uma página "Sobre", que continha informações sobre o criador.

Vamos utilizar também a *tag* `a` e o atributo `href` para criar um *hyperlink* entre a página principal e a página *about*.

```html
<!-- arquivo principal -->
<a href="views/about.html">Sobre</a>
```

Vamos fazer o mesmo para a página *about*, supondo que o nome do arquivo da página principal seja `index.html`.

```html
<!-- about.html -->
<a href="../index.html">Início</a>
```

Novamente, isso funciona pois estamos utilizando o sistema de arquivos.

#### Escrevendo código HTML

Resumidamente, ao escrever código HTML você deve se preocupar principalmente com três coisas:

- Quais elementos devem estar presentes no *site*.
- Qual a hierarquia entre eles.
- Estruturar o layout de modo a facilitar o código CSS.

Há uma quarta preocupação quanto à semântica dos elementos, como o uso de `header` e `footer` no lugar de `div`, mas não é algo tão importante, especialmente nesse começo de aprendizado.

É importante reforçar que **não se estiliza páginas com HTML**. Um erro muito comum de *devs* iniciantes é utilizar as *tags* `h1 .. h6` baseadas em seu tamanho, sendo que este pode ser alterado facilmente via CSS. Essas *tags* devem ser utilizada apenas para estabelecer uma hierarquia entre os textos de sua página, o que significa que o uso delas tem mais a ver com a semântica do *site*.

**Observação:** Note que no exemplo do *tweet* foi utilizada a *tag* `h2`. Isso porque é boa prática cada página possuir um único `h1`, e como espera-se que hajam vários *tweets* dentro de um *site*, optei pela utilização do `h2`.

---



### CSS

---

O código CSS, como foi dito anteriormente, serve para estilizar a página. Com ele, vamos fazer o nosso *tweet* criado ficar "com cara" de *tweet*.

#### Onde escrever CSS

Há 3 opções:

- direto no atributo `style` do elemento, o que é extremamente não recomendado.

  ```html
  <p style="color: red">Texto vermelho</p>
  ```

- dentro de uma *tag* `style`.

  ```html
  <head>
      <style>
          p {
              color: red;
          }
      </style>
  </head>
  <body>
      <p>Todos os parágrafos</p>
      <p>Ficaram vermelhos</p>
  </body>
  ```

- dentro de um arquivo de extensão `.css`, em conjunto com a *tag* `link`.

  ```html
  <!-- index.html -->
  <head>
  	<link rel="stylesheet" href="styles.css" />
  </head>
  <body>
      <p>Todos os parágrafos</p>
      <p>Ficaram vermelhos</p>
  </body>
  ```

  ```css
  /* styles.css */
  p {
      color: red;
  }
  ```

A utilização ou não de um arquivo externo para o CSS depende de bom senso e padrão de projeto. Para códigos pequenos, facilita fazer no próprio arquivo `.html`.

**Observação:** Projetos maiores costumam ser complicados de desenvolver com HTML e CSS puros. Existem soluções, como *React.js*, que facilitam o desenvolvimento de *websites* complexos.

**Observação 2:** Note que o comentário em CSS possui uma sintaxe diferente do HTML.

#### *Rules* CSS

Em média, mais que 95% do código CSS puro são regras (*rules*). Segue a sintaxe de uma regra:

```css
seletor {
    propriedade1: valor1;
    propriedade2: valor2;
    ...
}
```

O "seletor" serve para identificar a quais elementos do DOM essa regra se aplica. As chaves representam o "bloco de declaração". Cada linha terminada em `;` é uma "declaração", composta por "propriedade" e "valor".

Cada conjunto propriedade-valor altera um aspecto da estilização dos elementos selecionados pelo seletor.

#### Id e Class

Suponhamos em nosso exemplo anterior dos parágrafos que queremos que apenas um parágrafo particular fique da cor vermelho. Podemos definir um atributo `id` para ele e selecioná-lo via CSS.

```html
<!-- index.html -->
<p>Nem todos os parágrafos</p>
<p id="vermelho">Ficaram vermelhos</p>
```

```css
/* styles.css */
#vermelho {
    color: red;
}
```

Vamos supor agora que temos 5 parágrafos, e queremos que apenas o primeiro e o terceiro fiquem vermelhos. Podemos utilizar para isso o atributo `class`. A principal diferença entre os dois é que pode haver múltiplos elementos da mesma classe, enquanto o id deve ser associado a um único elemento dentro da página.

```html
<!-- index.html -->
<p class="vermelho">Parágrafo 1</p>
<p>Parágrafo 2</p>
<p class="vermelho">Parágrafo 3</p>
<p>Parágrafo 4</p>
<p>Parágrafo 5</p>
```

```css
/* styles.css */
.vermelho {
    color: red;
}
```

Então utilizamos no seletor o caractere

- `#` para `id`
- `.` para  `class`
- nada para tipo de elemento

#### Combinando seletores

Podemos combinar seletores de várias formas. Serão apresentadas três delas:

- Concatenando seletores

  ```html
  <!-- index.html -->
  <p class="vermelho">Parágrafo com classe "vermelho"</p>
  <h1 class="vermelho">Título com classe "vermelho"</p>
  ```

  ```css
  /* styles.css */
  h1.vermelho {
      color: red;
  }
  ```

  Nesse caso, as regras se aplicarão apenas àqueles elementos que se encaixarem em todos os seletores concatenados.

- Colocando vírgulas entre os seletores

  ```html
  <!-- index.html -->
  <p>Parágrafo</p>
  <h1>Título</p>
  ```

  ```css
  /* styles.css */
  p, h1 {
      color: red;
  }
  ```

  Nesse caso, as regras se aplicarão aos elementos que se encaixarem em pelo menos um dos seletores separados por vírgula.

- Colocando um espaço entre os seletores

  ```html
  <!-- index.html -->
  <p>Parágrafo</p>
  <h1>Título</p>
  ```

  

  ```css
  /* styles.css */
  p, h1 {
      color: red;
  }
  ```

  



**Observação:** O assunto "seletor" é muito mais profundo do que aquilo que foi apresentado aqui, e há muitas informações importantes que foram deixadas de lado por enquanto. O tempo é curto e infelizmente não dá para abordar tudo agora, no entanto, as ferramentas apresentadas já são bem poderosas. 

#### DevTools - Elements



---



### JavaScript

---



---



### Sistemas Web

---



---

