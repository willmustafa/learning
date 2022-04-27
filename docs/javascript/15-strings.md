---
layout: default
title: Strings
nav_order: 15
parent: Javascript
---

# STRINGS

Uma string inevitavelmente precisará ser tratada, comparada ou alterada.

## Remover e trocar palavras

Para trocar uma palavra em uma string ou remove-la, utilize `.replace(palavraParaMudarNaString, stringNova)` ou `.replaceAll(palavraParaMudarNaString, stringNova)`:

```
// Pode ser utilizado REGEXP
str.replace(REGEXP, NEWSTRING)

// Ou utilizar uma string comum
let str = "Quero um emprego"
str.replace('emprego', 'cachorro') // "Quero um cachorro"

// .replace altera apenas a primeira ocorrência, para editar todas, utilize .replaceAll
str = "batata, feijão, batata frita, batata assada"
str.replaceAll('batata', 'mandioca') // "mandioca, feijão, mandioca frita, mandioca assada"
```

> Lembre-se: replace é case sensitive, ou seja, se o input vir pelo usuário, primeiramente transforme-a em minúsculo e depois faça o replace.

Você também pode substituir uma quantidade fixa de caracteres com `.substring(indexStart, indexEnd[opcional])`:

```
let str = "- Marca: LG"
str.substring(2, str.length) // "Marca: LG"
str.substring(str.length - 2) // "LG"
```

## minúsculo e MAIÚSCULO

Para transformar uma string em maiúsculo e minúsculo é muito simples, apenas utilize `.toLowerCase()` ou `.toUpperCase()`:

```
let str = "Willian Felipe MusTaFa"

str.toLowerCase() // "willian felipe mustafa"

str.toUpperCase() // "WILLIAN FELIPE MUSTAFA"
```

## Remover espaços em branco no início e final

As vezes uma string pode vir com espaços ou tabulações no início ou final e precisam ser removidas, ou ainda uma string passa por uma substring ou replace e sobram espaços, para isso o comando `.trim()` fará a limpeza:

```
let str = "willian felipe mustafa"
str.replace("willian", "") // " felipe mustafa"

str.replace("willian", "").trim() // "felipe mustafa"
```

Alternativamente, você pode remover os espaços apenas no início `.trimStart()` ou no final `.trimEnd()`.

## Dividir uma string e retornar array

Uma string com divisores como um `.csv` que é separado por vírgulas, pode ser transformada em uma array com `.split(separador, limite[opcional])`:

```
let str = "item 1, item 2, item 3"
str.split(',') // ["item 1", "item 2", "item 3"]
```

## Checar se a string contêm uma palavra

Utilize `.includes(palavraProcurada)` para retornar um boolean.

```
let str = "placa de video rtx 3090 asus rog"

str.includes('rtx') // true
```

As vezes, será necessário verificar se a palavra contem uma das palavras dentro de uma array, por exemplo, a frase "placa de video rtx 3090 asus rog" contem uma das marcas ["asus", "evga", "msi"]

```
let marcas = ["asus", "evga", "msi"]
let str = "placa de video rtx 3090 asus rog"

marcas.filter(marca => str.includes(marca)) // ["asus"]

```

## Regexp

Para encontrar uma correspondência entre uma string e uma expressão regular (regexp), utiliza-se `.match(regexp)`:

```
var str = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz";
var regexp = /[A-E]/gi;
var matches_array = str.match(regexp);

console.log(matches_array);
// ['A', 'B', 'C', 'D', 'E', 'a', 'b', 'c', 'd', 'e']
```