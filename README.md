<h1 align="center">
    <img alt="GoStack" src="https://rocketseat-cdn.s3-sa-east-1.amazonaws.com/bootcamp-header.png" width="200px" />
</h1>

<h3 align="center">
  Desafio 4: Introdução ao React
</h3>

<blockquote align="center">“Sucesso não é o resultado de um jogo, mas o destino de uma jornada”!</blockquote>

<p align="center">
  <img alt="GitHub language count" src="https://img.shields.io/github/languages/count/rocketseat/bootcamp-gostack-desafio-04?color=%2304D361">

  <img alt="License" src="https://img.shields.io/badge/license-MIT-%2304D361">

</p>

<p align="center">
  <a href="#rocket-sobre-o-desafio">Sobre o desafio</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-entrega">Passo a Passo</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#memo-licença">Licença</a>
</p>

## :rocket: Sobre o desafio

Crie uma aplicação do zero utilizando **Webpack, Babel, Webpack Dev Server e ReactJS**.

Nessa aplicação você irá desenvolver uma **interface** semelhante com a do **Facebook** utilizando React.

As informações contidas na interface são **estáticas** e não precisam refletir nenhuma API REST ou back-end.

### Tela da aplicação

![Facebook](.github/facebook.png)

O layout não precisa ficar exatamente igual, você pode utilizar sua criatividade para modificar da maneira que preferir.

O mais importante é que todos elementos apareçam em tela.

O layout da aplicação está [nesse link](.github/layout.sketch) que pode ser aberto por essa ferramenta gratuita e online: https://www.figma.com/

### Componentes

Na imagem abaixo destaquei cada componente que você criará e abaixo da imagem está a descrição e responsabilidades de cada um:

![Componentes](.github/components.png)

**Header (Amarelo):** Responsável por exibir a logo e o link para acessar o perfil;

**PostList (Verde):** Responsável por armazenar os dados da listagem de post, esses dados devem ficar dentro do `state` do componente e não em uma variável comum, por exemplo:

```js
class PostList extends Component {
  state = {
    posts: [
      {
        id: 1,
        author: {
          name: "Julio Alcantara",
          avatar: "http://url-da-imagem.com/imagem.jpg",
        },
        date: "04 Jun 2019",
        content: "Pessoal, alguém sabe se a Rocketseat está contratando?",
        comments: [
          {
            id: 1,
            author: {
              name: "Diego Fernandes",
              avatar: "http://url-da-imagem.com/imagem.jpg",
            },
            content: "Conteúdo do comentário",
          },
        ],
      },
      {
        id: 2,
        // Restante dos dados de um novo post
      },
    ],
  };
}
```

**Post (Vermelho):** Responsável por exibir os dados do post, esses dados devem vir através de uma propriedade recebida do componente PostList, ou seja, lá no PostList você terá algo assim:

```js
posts.map((post) => <Post key={post.id} data={post} />);
```

**Comment (Azul):** Responsável por exibir um comentário. Os dados do comentário virão por uma propriedade do componente. Dentro do componente Post você terá um novo `.map` para listar os comentários do post:

```js
data.comments.map((comment) => <Comment key={comment.id} data={comment} />);
```

## 📅 Passo a Passo

1. Iniciar projeto com:

```
yarn init -y
```

2. Instalar dependências do babel e webpack

```
yarn add @babel/core @babel/preset-env @babel/preset-react webpack webpack-cli -D
```

3. Instalar react e react-dom

```
yarn add react react-dom
```

4.Criar arquivo de configuração do babel (babel.config.js)

```
module.exports = {
  presets: ["@babel/preset-env", "@babel/preset-react"],
};
```

5.Criar arquivo de configuração do webpack (webpack.config.js)

```
console.log('nhaa')
```

6. Adicionar script de build no package.json

```
"scripts" : {
  "build": "webpack --mode development"
}
```

7. Criar o arquivo index.html na pasta public, escrever estrutura básica do html 5 e importar o bundle.js

8. Instalar biblioteca para reiniciar automaticamente o servidor ao salvar o código.

```
yarn add webpack-dev-server -D
```

9. Adicionar script de dev no package.json

```
"script": {
  "dev": "webpack-dev-server --mode development"
}
```

## :memo: Licença

Esse projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE.md) para mais detalhes.

---

Feito com ♥ by Ryan Alencar :wave: [Instagram](https://www.instagram.com/ryanalencar_1701/?hl=pt-br)
