# Basic Hook - useEffect

## O que é um Hook?
 Um Hook é uma função especial que te permite utilizar recursos do React. Por exemplo, useState é um Hook que te permite adicionar o state do React a um componente de função. Vamos aprender outros Hooks mais tarde.

O Effect Hook (Hook de Efeito) te permite executar efeitos colaterais em componentes funcionais:

```js
import React, { useState, useEffect } from 'react';

function Exemplo() {
  const [count, setCount] = useState(0);

  // Similar ao componentDidMount e componentDidUpdate:
  useEffect(() => {
    // Atualiza o título do documento usando a API do browser
    // Sempre quando houve atualização nos states, useEffect será executado.
    document.title = `Você clicou ${count} vezes`;
  });

  return (
    <div>
      <p>Você clicou {count} vezes</p>
      <button onClick={() => setCount(count + 1)}>
        Clique aqui
      </button>
    </div>
  );
}
```

fazer algo apenas depois da renderização. O React ira se lembrar da função que você passou (nos referiremos a ele como nosso “efeito”), e chamá-la depois que realizar as atualizações do DOM. Nesse efeito, mudamos o título do documento, mas podemos também realizar busca de dados ou chamar alguma API imperativa.

Por que useEffect é chamado dentro de um componente? Colocando useEffect dentro do componente nos permite acessar o state count (ou qualquer outra prop) direto do efeito. Nós não precisamos de uma API especial para lê-los — já está no escopo da função. Hooks adotam as closures do JavaScript e evitam APIs especificas do React onde o JavaScript já provê uma solução.

useEffect executa depois de toda renderização? Sim! Por padrão, ele roda depois da primeira renderização e depois de toda atualização. (Falaremos sobre como customizar isso depois.) Em vez de pensar em termos de “montando” (“mounting”) e “atualizando” (“updating”), você pode achar mais fácil pensar que efeitos acontecem “depois da renderização”. React garante que o DOM foi atualizado na hora de executar os efeitos.

Dica: Otimizando a Performance ao Pular Efeitos
Em alguns casos, limpar ou aplicar o efeito em cada renderização pode criar um problema de performance. Em componentes de classes, nós resolvemos isso escrevendo uma comparação extra com prevProps ou prevState dentro do componentDidUpdate:

Esse requerimento é comum o bastante para estar embutido na API do Hook useEffect. Você pode dizer ao React para pular a aplicação de um efeito se certos valores não tiverem mudado entre as renderizações. Para fazer isso, passe uma array como um segundo argumento opcional ao useEffect:

```js 
useEffect(() => {
  document.title = `Você clicou ${count} vezes`;
}, [count]); // Apenas re-execute o efeito quando o count mudar
```

Para mais informações acesse a [documentação oficial do react](https://pt-br.reactjs.org/docs/hooks-effect.html).
