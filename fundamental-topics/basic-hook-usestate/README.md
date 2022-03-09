# Basic Hook - useState

## O que é um Hook?
 Um Hook é uma função especial que te permite utilizar recursos do React. Por exemplo, useState é um Hook que te permite adicionar o state do React a um componente de função. Vamos aprender outros Hooks mais tarde.

Quando utilizamos classe para fazer um component em react para utilizamos state devemos fazer desta forma:

```js
class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }
```

O que não possível no modelo component função, ai que entra os hooks, resumindo são funcoes especiais que nos permite usar recursos do react, e para utilizar este hook (useState) basta:

```js
import React, { useState } from 'react';

function Example() {
  const [count, setCount] = useState(0);
```

Deixando mais semântico e mais logico, pode se dizer que segue o mesmo fluxo do component class, porem nomeamos quem será a função responsável por atualizar um estado em específico.

Para a declaração dele ele pede apenas um parâmetro, que seria o valor inicial dele. Após sua criação basta usar a função nomeada para atualizar o state, neste exemplo para alterar o valor do 'count' basta:

```js
function alterStateCount() {
  setCount(count + 2); // -> 2
}
```

Facilitando também na hora de utilizar este state.

O que no component classe seria:
```html
<p>{this.state.count}</p>
```

No component function utilizando useState ficaria:

```html 
<p>{count}</p>
```


Para mais informações acesse a [documentação oficial do react](https://pt-br.reactjs.org/docs/hooks-state.html).
