# Questões Teóricas sobre React Hooks

1. O que são Hooks no React? 
Hooks são funções que permitem que você use o estado e outros recursos do React sem precisar escrever uma classe.

2. O que é a função do Hook `useState` e como ele é utilizado? 
A função do Hook `useState` é usada para adicionar estado a componentes funcionais. Ele retorna um par: o estado atual e uma função para atualizá-lo.

3. Como o Hook `useEffect` funciona e para que ele é utilizado? 
O Hook `useEffect` permite que você realize efeitos colaterais em componentes funcionais, como chamadas a APIs, manipulação de eventos e atualizações do DOM.

4. O que são dependências no `useEffect` e como elas afetam o comportamento do Hook? 
Dependências no `useEffect` são valores que o Hook observa para determinar se deve executar o efeito novamente. Se algum valor de dependência mudar, o efeito será reexecutado.

5. Qual é a diferença entre `useEffect` e `componentDidMount`? 
 `useEffect` pode ser usado para simular `componentDidMount`, `componentDidUpdate` e `componentWillUnmount` dependendo de suas dependências, enquanto `componentDidMount` é chamado apenas uma vez após a montagem.

6. Para que serve o Hook `useContext`? 
O Hook `useContext` é utilizado para acessar o contexto do React, permitindo que componentes funcionais leiam e assinem atualizações de contexto.

7. O que é o Hook `useReducer` e quando você deve usá-lo em vez de `useState`? 
 `useReducer` é um Hook para gerenciar estados complexos e é útil quando o estado tem uma lógica de atualização mais complexa ou quando o próximo estado depende do anterior.

8. Qual é a importância da regra dos Hooks e como você deve segui-la? 
A regra dos Hooks garante que os Hooks sejam chamados na mesma ordem em todas as renderizações, evitando comportamentos imprevisíveis. Eles devem ser chamados no nível superior de um componente ou de outros Hooks.

9. O que é o Hook `useMemo` e quando você deve usá-lo? 
 `useMemo` é um Hook que memoiza um valor calculado para evitar recalcular em renderizações, sendo útil para otimizar desempenho em funções pesadas.

10. Qual é a função do Hook `useCallback` e como ele difere do `useMemo`? 
 `useCallback` memoiza uma função para evitar que ela seja recriada em cada renderização, enquanto `useMemo` memoiza o resultado de uma função. Ambos ajudam a otimizar o desempenho.

11. Qual é a diferença entre `useState` e `useReducer` no gerenciamento de estado? 
 `useState` é ideal para estados simples e locais, enquanto `useReducer` é mais apropriado para estados complexos que envolvem múltiplas sub-valores ou que têm lógica de atualização complexa.

12. O que é o ciclo de vida de um componente em React? 
O ciclo de vida de um componente em React refere-se aos diferentes estágios pelos quais um componente passa desde sua criação até sua remoção do DOM.

13. Quais são as principais fases do ciclo de vida de um componente de classe em React? 
As principais fases são: Montagem (mounting), Atualização (updating) e Desmontagem (unmounting).

14. Como o método componentDidMount é utilizado e qual é seu propósito? 
 `componentDidMount` é chamado logo após a montagem do componente. É usado para iniciar operações que requerem que o DOM esteja disponível, como chamadas de API.

15. O que o método shouldComponentUpdate faz e quando ele deve ser usado? 
 `shouldComponentUpdate` permite que você impeça a atualização de um componente com base nas mudanças de props ou estado, ajudando a otimizar o desempenho.

16. Qual é a função do método componentWillUnmount e quando ele é chamado? 
 `componentWillUnmount` é chamado imediatamente antes de um componente ser desmontado e é utilizado para limpar recursos, como timers ou assinaturas.

17. O que acontece se você tentar alterar o estado diretamente no método render de um componente de classe? 
Alterar o estado diretamente no método render pode causar um loop infinito de re-renderizações, resultando em um comportamento inesperado e travamento da aplicação.

18. Analise o código a seguir: 

```javascript
import React, { useState } from 'react'; 

function Counter() { 
  const [count, setCount] = useState(0); 

  return ( 
    <div> 
      <p>Current count: {count}</p> 
      <button onClick={() => setCount(count + 1)}>Increment</button> 
      <button onClick={() => setCount(count - 1)}>Decrement</button> 
    </div> 
  ); 
} 

export default Counter; 
```

O que acontece quando o botão "Increment" é clicado? E o botão "Decrement"? 
Quando o botão "Increment" é clicado, a função `setCount` é chamada com `count + 1`, atualizando o estado `count`. Para o botão "Decrement", `setCount` é chamado com `count - 1`, reduzindo o valor de `count`. Ambos os cliques causam uma re-renderização do componente com o novo valor.

Como o estado count é atualizado e refletido na interface do usuário? 
O estado `count` é atualizado através do Hook `useState`, e o React re-renderiza o componente automaticamente quando o estado muda, refletindo o novo valor na interface.

O que aconteceria se o useState fosse removido do código? Como isso afetaria o comportamento do componente? 
Se `useState` fosse removido, o componente não teria estado para gerenciar o contador, resultando em um valor fixo de `count` sempre igual a zero, e os botões não teriam efeito.
"""
