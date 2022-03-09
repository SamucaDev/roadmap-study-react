# Components

## Conceito

Componentes permitem você dividir a UI em partes independentes, reutilizáveis e pensar em cada parte isoladamente. Essa página fornece uma introdução à ideia de componentes.
Conceitualmente, componentes são como funções JavaScript. Eles aceitam entradas arbitrárias (chamadas “props”) e retornam elementos React que descrevem o que deve aparecer na tela.

### Componentes de Função

```js
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

Essa função é um componente React válido porque aceita um único argumento de objeto “props” (que significa propriedades) com dados e retorna um elemento React. Nós chamamos esses componentes de “componentes de função” porque são literalmente funções JavaScript.

---

### Componentes de Classe

```js
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

Essa função é um componente válido, escrito no formato de classe, assim como é feito no javaScript.

---

Ambus são funcionais porém dividem diferenciais que são apresentados nos próximos capitulos.

## Renderizando componentes

Um exemplo bem objetivo de implementação de um componentes seria da seguinte forma:

```js
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="Sara" />;
ReactDOM.render(element, document.getElementById("root"));
```

ou

```js
function Comment(props) {
  return (
    <div className="Comment">
      <div className="UserInfo">
        <img
          className="Avatar"
          src={props.author.avatarUrl}
          alt={props.author.name}
        />
        <div className="UserInfo-name">{props.author.name}</div>
      </div>
      <div className="Comment-text">{props.text}</div>
      <div className="Comment-date">{formatDate(props.date)}</div>
    </div>
  );
}
```

Para mais informações acesse a [documentação oficial do react](https://pt-br.reactjs.org/docs/components-and-props.html).
