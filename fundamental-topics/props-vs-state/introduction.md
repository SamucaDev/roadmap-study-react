# Props vs State

O state do componente é similar as props, mas é privado e totalmente controlado pelo componente.

Exemplo de uso de state:

```js
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = { date: new Date() };
  }

  componentDidMount() {}

  componentWillUnmount() {}

  render() {
    return (
      <div>
        <h1>Hello, world!</h1>
        <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
      </div>
    );
  }
}
```

Temos 2 métodos, que são de extrema importancia:

- componentDidMount() - é executado depois que a saída do componente é renderizada no DOM.

- componentWillUnmount() - O método componentWillUnmount() nos permite executar o código React quando o componente é destruído ou desmontado do DOM (Document Object Model).

## Se aprofundando no state

Não Modifique o State Diretamente

```js
// Errado
this.state.comment = "Hello";
```

```js
// Correto
this.setState({ comment: "Hello" });
```

PS: o único lugar que é permitido modificar o state é no construtor

## Se aprofundando em props

Basicamente utilizamos props para passar informações para um componente filho.

```js
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="Sara" />;
ReactDOM.render(element, document.getElementById("root"));
```

Para mais informações acesse a [documentação oficial do react](https://pt-br.reactjs.org/docs/state-and-lifecycle.html).
