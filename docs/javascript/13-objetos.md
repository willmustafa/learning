---
layout: default
title: Objetos
nav_order: 13
parent: Javascript
---

# Javascript Orientado a Objetos

Um objeto é um conjunto de propriedades e métodos estruturados em uma única variável ou elemento.

O exemplo a seguir cria um objeto:

```
let pessoa = {
    nome: 'Willian',
    sobrenome: 'Mustafa',
    idade: '27'
};
```

Para acessar uma propriedade, pode ser usado o nome da variável e um ponto ou a variável e o nome da propriedade uma array:

```
let pessoa = {
    nome: 'Willian',
    sobrenome: 'Mustafa',
    idade: '27'
};
console.log(pessoa.nome) // Exibe Willian

console.log(pessoa['nome']) // Exibe Willian
```

Uma propriedade com espaço precisa ser colocada entre aspas e só pode ser acessada via array.

Você também pode alterar o valor de uma propriedade como se fosse uma variável comum:

```
let pessoa = {
    nome: 'Willian',
    sobrenome: 'Mustafa',
    idade: '27'
};
pessoa.nome = 'Thaila'; // Altera o nome da variável pessoa
```

Você também pode inserir funções dentro de um objeto, chamados de métodos:

```
let pessoa = {
    nome: 'Willian',
    sobrenome: 'Mustafa',
    idade: '27',
    digaOi: function(){ // ES6 pode ser escrito como "digaOi(){"
        console.log('Oi!');
    }
};

pessoa.digaOi(); // Imprime: Oi!
```

A utilização de linguagem orientada a objetos é sempre recomendada por criar um ambiente que facilita o desenvolvimento e manutenção do código. Uma implementação muito utilizada para isso são as **Classes**.

* * *

## Class

Uma classe é um tipo de função que haje como um objeto. A seguir são demonstradas diversas possibilidades usando uma classe e explicadas a seguir.

```
class Pessoa{
    constructor(inp_nome, inp_sobrenome) {
        this.nome = inp_nome;
        this.sobrenome = inp_sobrenome;
    }

    // um Getter pode ser usado para chamar qualquer propriedade ou um conjunto de propriedades onde se espera que uma ordem seja seguida, como no exemplo abaixo
    get nomeCompleto() {
        return this.nome + ' ' + this.sobrenome;
    }

    digaOi() {
        console.log('Oi!');
    }

    // Método static não pode ser acessado fora do contexto de uma classe
    static quantidadeLetras(){
        return this.nome.length
    }
}

let funcionario = new Pessoa('Renato', 'Silva');

console.log(funcionario.nome); // Renato
console.log(funcionario.nomeCompleto); // Renato Silva

funcionario.digaOi(); // Oi!

funcionario.quantidadeLetras(); // TypeError, um método static não pode ser acessado de fora da classe
```

## Percorrendo Objetos

Objetos possuem métodos especiais para iterar suas propriedades, como **For...In**, **Object.keys()**, etc.

**For...in**

Utilizado para fazer um loop entre as propriedades do objeto.

```
for(let prop in funcionario){
    console.log(prop);
    console.log(funcionario[prop]);
}
// nome
// Renato
// sobrenome
// Silva
```

**Object.keys()**

Utilizado para retornar uma array com todas as propriedades do objeto.

```
console.log(Object.keys(funcionario)) // Array ["nome", "sobrenome"]
```

**Object.values()**

Utilizado para retornar uma array com todos os valores nas propriedades do objeto.

```
console.log(Object.values(funcionario)) // Array ["Renato", "Silva"]
```

**Object.entries()**

Transforma o objeto em uma array em um par [propriedade, valor].

```
console.log(Object.entries(funcionario)) // Array [["nome", "Renato"], ["sobrenome", "Silva"]]
```