---
layout: default
title: Teste Estrutural
nav_order: 1
parent: Teste de Software
grand_parent: Engenharia de Software
---

# Teste Estrutural ou Teste de Caixa Branca

Baseado na inspeção do código fonte, mas nem sempre, o programa pode ser abstraido em uma forma de um grafo de fluxo de controle.

Um programa pode ser representado em um grafo da seguinte maneira:

- Um programa **P** é dado por **G = (N, A, e, s)**

Onde:

- **N** é o conjunto de nós
- **A** é o conjunto de arcos (ou arestas)
- o nó **e** é a única entrada e o nó **s** é a única saída

Um nó **n** representa uma instrução simples (comando) ou uma sequência de instruções executadas como um bloco de comando, como por exemplo:

```
troca = v[esq];
v[esq] = v[dir];
v[dir] = troca;
esq = esq + 1;
dir = dir - 1;
```

Cada arco **A** é um par ordenado (n,m) de nós que representa uma mudança de controle do nó **n** para o nó **m**, como por exemplo:

```
while (esq <= dir){
    while(v[esq] < pivo){
        esq = esq + 1;
    }
    while(v[dir] > pivo){
        dir = dir - 1;
    }
    if(esq <= dir){
        troca = v[esq];
        v[esq] = v[dir];
        v[dir] = troca;
        esq = esq + 1;
        dir = dir - 1;
    }
}
```

## Caminhos / Comportamentos

Um **caminho** do programa é representado por uma sequência finita de nós (n1, n2, ..., nk);

Um **caminho completo** é um caminho cujo nó inicial é o nó de entrada e o final é o nó de saída;

Um **caminho simples** é um caminho cujo nós são distintos;

Um caminho é **livre de laços** se todos os seus nós são distintos;

## Fluxograma do MDC (Máximo Divisor Comum)

```
public int Euclides(int m, int n){
    int r;

    // Nó 0
    if(n > m){

        // Nó 1
        r = m;
        m = n;
        n = r;
    }

    // Nó 2
    r = m%n;

    // Nó 3
    while(r!=0){

        // Nó 4
        m = n;
        n = r;
        r = m%n;
    }

    // Nó 5
    return n;
}
```

Grafo:

![](/learning/docs/eng-software/teste/resources/diagrama-mdc.png?raw=true)

Alguns exemplos de teste estrutural:

- Teste baseado em fluxo de controle (estruturas de condições, desvios, loops)
- Teste baseado em fluxo de dados (estrutura de dados)
- Teste baseado em complexidade

## Fluxo de Controle

No fluxo de controle, o critério a ser escolhido irá gerar qual o tipo de teste você precisará criar: passar por todos os nós, todas as arestas e todos os caminhos.

## Fluxo de Dados

## Fluxo de Complexidade