---
layout: default
title: Tipos de Variáveis
nav_order: 12
parent: Javascript
permalink: docs/javascript/variaveis
---

# Tipos de Variáveis

O javascript é dinamicamente tipado, ou seja, ele não precisa que a variável tenha seu tipo declarado, como por exemplo string, int ou float, porque ele faz essa implementação por baixo dos panos. Mas ainda sim precisamos declarar a variável utilizando um dos seguintes operadores:

- var
- let
- const

## Hoisting ou Içamento

O javascript puxa todas as variáveis **var** para o topo da execução de seu escopo, mas apenas a declaração e não o seu valor implementado. Ou seja, você pode utilizar o seguinte código (apesar de não ser aconselhável):

```
aba = "sim";
var aba;
console.log(aba); // Exibe: sim
```

## VAR

Essa variável poderá ser lida de qualquer lugar no código (escopo global) e também pode ser modificada a qualquer momento.
O ECMA2015 define que a sua utilização se tornou uma má prática, já que a liberdade à modificações podem levar a problemas de segurança e bugs de redeclaração.

## LET

O **let** é executado apenas dentro do bloco onde é declarada, ou seja, dentro de uma função, loop ou condicional.

```
function() {
	let processador = “AMD”;
	console.log(processador); // Exibe o texto: AMD
}

console.log(processador); // Gera um ERRO, pois nesse contexto a variável não está declarada
```

## CONST

A variável (ou constante) **const** é uma variável cujo valor só pode ser definido em sua declaração e também é apenas executado apenas dentro do escopo.

```
const fruta = "maçã";
fruta = "uva"; // Gera um erro por não ser possível mudar o valor da variável
```

## Resumo

| Escopo       | CONST          | LET      | VAR    |
|:-------------|:------------------|:------|:------|
| Global         | Não | Não  | Sim |
| Função | Sim | Sim  | Sim |
| Bloco           | Sim | Sim  | Não |
| Pode ser redefinido? | Não | Sim  | Sim |