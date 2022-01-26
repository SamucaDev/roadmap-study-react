# JSX

## Conceito

Traduzido do inglês-JSX é uma extensão React para a sintaxe da linguagem JavaScript que fornece uma maneira de estruturar a renderização de componentes usando uma sintaxe familiar a muitos desenvolvedores. É semelhante em aparência ao HTML. Wikipedia (inglês)

Exemplo de um código JSX: Esta sintaxe estranha de tags não é uma string, nem HTML.

```js
const element = <h1>Hello, world!</h1>;
```

Tudo que é válido no JavaScript, pode ser implementado no JSX.

```js
function formatName(user) {
  return user.firstName + " " + user.lastName;
}

const user = {
  firstName: "Harper",
  lastName: "Perez",
};

const element = <h1>Hello, {formatName(user)}!</h1>;

ReactDOM.render(element, document.getElementById("root"));
```


## Especificando Atributos com JSX

Você pode usar aspas para especificar strings literais como atributos:

```js
const element = <a href="https://www.reactjs.org"> link </a>;
```

Você também pode usar chaves para incorporar uma expressão JavaScript em um atributo:

```js
const element = <img src={user.avatarUrl}></img>;
```

Quer se aprofundar? [Artigo oficial React.](https://pt-br.reactjs.org/docs/introducing-jsx.html)