# Listas e chaves

Relembrando listas do javascript

```js
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map((number) => number * 2);
console.log(doubled);

// [2, 4, 6, 8, 10]
```

Colocando no contexto do react, vamos renderizara multiplos componentes usando listas

```js
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);

```

Renderizando...

```js
ReactDOM.render(
  <ul>{listItems}</ul>,
  document.getElementById('root')
);
```

Outro exemplo utilizando passando essa lista por props

```js
function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>
    <li>{number}</li>
  );
  return (
    <ul>{listItems}</ul>
  );
}

const numbers = [1, 2, 3, 4, 5];
ReactDOM.render(
  <NumberList numbers={numbers} />,
  document.getElementById('root')
);
```

## Incluindo chaves na renderização desta lista

### Por que devemos colocar keys nos elementos?

As chaves ajudam o React a identificar quais itens sofreram alterações, foram adicionados ou removidos. As chaves devem ser atribuídas aos elementos dentro do array para dar uma identidade estável aos elementos:

```js
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li key={number.toString()}>
    {number}
  </li>
);
```

Boas práticas: Sempre escolher uma string que seja única para identificar o elemento.

### Exemplo de utilizacao utilizando component function

```js
function NumberList(props) {
  const numbers = props.numbers;
  return (
    <ul>
      {numbers.map((number) =>
        <ListItem key={number.toString()}
                  value={number} />
      )}
    </ul>
  );
} 
```
