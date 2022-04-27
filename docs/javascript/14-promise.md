---
layout: default
title: Promise
nav_order: 14
parent: Javascript
---

# Promessas

> As promessas são objetos usados para o processamento assíncrono. Uma `Promise` representa um valor que pode estar disponível agora, no futuro ou nunca. - [Mozilla](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Promise)

É utilizado quando uma função pode ter um retorno positivo ou negativo e precisam ser tratadas de forma separadas. Além de que é utilizada obviamente para funções assínconas.

```
let batata = new Promise(async (resolve, reject) => {
    //..
    // função que resolve algo e ativa a próxima linha
    const algo = await facaAlgo()

    if(algo == 'Deu bom'){
        resolve('Retorna algo aqui dentro pra ser usado la fora')
    }else{
        reject('Retorna um erro ou elemento para ser usado fora')
    }
})

batata.then(element => console.log(element)).catch(element => console.log(element))
```

## Promise.All

Em momentos específicos, será necessário aguardar que todas as promessas sejam completadas antes de dar seguimento no código, para isso, passa-se todas as promessas para dentro da `Promise.all` e o retorno será disparado após todas terminarem.

```
Promise.all([promise1, promise2, promise3]).then(valores => console.log(valores))
```