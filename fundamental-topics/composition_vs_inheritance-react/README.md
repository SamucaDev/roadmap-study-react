# Composição vs Herança

Desde já use composições.

Dentro de desenvolvimento temos alguns tipos de componentes que não sabemos quais serão os filhos deles, geralmente em *sidenav*, *headers*. Para atender isso o react nos disponibiliza através das propriedades o objeto *children*, exemplificado abaixo:

```js
function FancyBorder(props) {
  return (
    <div className={'FancyBorder FancyBorder-' + props.color}>
      {props.children}
    </div>
  );
}

function WelcomeDialog() {
  return (
    <FancyBorder color="blue">
      <h1 className="Dialog-title">
        Bem-vindo
      </h1>
      <p className="Dialog-message">
        Obrigado por visitar a nossa espaçonave!
      </p>
    </FancyBorder>
  );
}
```

Podemos trabalhar mais especificos, criando um componente e mandando 2 props para serem renderizadas:

```js
function SplitPane(props) {
  return (
    <div className="SplitPane">
      <div className="SplitPane-left">
        {props.left}
      </div>
      <div className="SplitPane-right">
        {props.right}
      </div>
    </div>
  );
}

function App() {
  return (
    <SplitPane
      left={
        <Contacts />
      }
      right={
        <Chat />
      } />
  );
}
```
