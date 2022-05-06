---
layout: default
title: Java
nav_order: 11
has_children: true
---

# Java

Todo código em Java é uma classe e suas funções sempre estão dentro de alguma classe.

Código básico em Java:

```
public class Programa{

    public static void main(String[] args){
        System.out.println("Olá mundo");
    }
}
```

Um código em Java precisa primeiro ser compilado para conseguir ser executado.

```
// Compila o arquivo Programa.java
javac Programa.java

// Executa o Programa compilado
java Programa
```

## Tipos e Variáveis

O Java é fortemente tipado, ou seja, toda variável precisa ter seu tipo declarado.

```
int idade = 28;
```

As variáveis são divididas entre primitivas e não primitivas.

Lista de variáveis primitivas possíveis:

- Boolean
- char
- byte
- short
- int
- long
- float
- double

Lista de variáveis não-primitivas possíveis:

- Class
- Object
- String
- Array
- Interface

Por ser fortemente tipado, você também precisará tipar o lado direito de um sinal de =, porque o Java le o resultado e depois insere esse valor na variável, então se ele ler (5 / 2) ele pensa que o resultado deve ser um inteiro e mesmo que a variável declarada seja double, ele irá realizar a conta em inteiro. Para resolver, você pode fazer (5.0 / 2), logo ele pensa em double, ou (float) 5/2 que é chamado de `casting`.

As variáveis são declaradas dentro do escopo, ou seja, se você criar uma variável dentro de um if, ela só existe dentro do if, não poderá ser utilizada em outra parte do código.

### Incremento

Em um loop, podemos utilizar uma das formas de incremento:

- contador += 1;
- contador++;
- ++contador;

