---
layout: default
title: Spread
nav_order: 11
parent: Javascript
permalink: docs/javascript/spread
---

# Spead operator

Spread ou espalhar, é um método de Javascript em que você pode espalhar o conteúdo de uma array dentro de outra array sem criar nesting.

```
let array1 = ['a','b','c']
let array2 = ['1','2','3']

let concatenado = [...array1, ...array2]
// [ "a", "b", "c", "1", "2", "3" ]
```

Também é possível utilizar spread com objetos, que torna muito útil para herdar propriedades ou inserir um novo objeto dentro de outro.

```
var obj1 = {titulo: 'Gabriel', informacoes: {idade: 27}}
var obj2 = {cidade: 'Ibiporã', salario: 5500}

console.log({...obj1.informacoes, ...obj2} )
  { 
      idade: 27, 
      cidade: "Ibiporã", 
      salario: 5500 
  }

// Inserindo direto no objeto 1
obj1.informacoes = {...obj1.informacoes, ...obj2}

console.log(obj1)
{
    titulo: "Gabriel",
    informacoes: { 
        idade: 27, 
        cidade: "Ibiporã", 
        salario: 5500 }
​}
```