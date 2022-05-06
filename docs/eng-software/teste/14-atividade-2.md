---
layout: default
title: Atividade 2 - Teste baseado em fluxo de controle
nav_order: 14
parent: Teste de Software
grand_parent: Engenharia de Software
---

# Atividade 2

Aluno: Willian Felipe Mustafa

Disciplina: Teste de Software

## 1.1 Requisitos

O objetivo é gerar testes para o QuickSort (na seção Suporte).

Vimos o teste estrutural, baseado em fluxo de controle. 

Lembrem-se dos critérios, todos os nós, todas as arestas e todos os caminhos.  

O grafo construído em aula para o Quick está atualizado (na seção Suporte). 

Dê os conjuntos de teste para cobertura dos critérios e, dê os códigos em Java para JUnit, que expressem o conjunto de teste gerado.

## 1.2 O Código a ser testado - QuickSort

O código Java do QuickSort fornecido é o seguinte:

```
package sort;

public class Quick {

    public static void quickSort(int v[], int esquerda, int direita) {
        int esq = esquerda;
        int dir = direita;
        int pivo = v[(esq + dir) / 2];
        int troca;

        while (esq <= dir) {
                while (v[esq] < pivo) {
                        esq = esq + 1;
                }
                while (v[dir] > pivo) {
                        dir = dir - 1;
                }
                if (esq <= dir) {
                        troca = v[esq];
                        v[esq] = v[dir];
                        v[dir] = troca;
                        esq = esq + 1;
                        dir = dir - 1;
                }
        }
        if (dir > esquerda)
                quickSort(v, esquerda, dir);

        if (esq < direita)
                quickSort(v, esq, direita);
    }
     
        public static void main(String args[]) {

            //int vetor[] = { 100, 15, 65, 65, 76, 3, 4, 6, 8, 89 };

            int quantidade = 100;
               int[] vetor = new int[quantidade];
               for (int i = 0; i < vetor.length; i++) {
                  vetor[i] = (int) (Math.random()*quantidade);
               }

           for (int i = 0; i < vetor.length; i++) {
                   System.out.println(" " + vetor[i]);
           }
            
           System.out.println(" ===================================== ");
           
           quickSort(vetor, 0, vetor.length - 1);

           for (int i = 0; i < vetor.length; i++) {
                    System.out.println(" " + vetor[i]);
            }
    }
}
```

## 2.0 Grafo de Fluxo de Controle

![](/learning/docs/eng-software/teste/resources/grafo-atividade2.png?raw=true)

## 2.1 Teste Estrutural

O teste estrutural, também conhecido como teste de caixa-branca, é projetado em função da estrutura interna do sistema, ou seja, seu desenvolvimento se dá analisando o código-fonte e do grafo acima. No teste estrutural baseado em fluxo de controle, temos 3 critérios:

- Critério Todos-Nós: A execução do programa precisará que todos os nós sejam executados pelo menos uma vez;
- Critério Todas-Arestas: Todos os arcos (desvio) deve ser executada pelo menos uma vez;
- Critério Todos-Caminhos: Requer que todos os caminhos possíveis sejam executados.

## 2.2 Critério Todos-Nós

0, 1, 2, 3, 2, 4, 5, 4, 6, 7, 1, 8, 9, 10, 11, 0, 1, 8, 9, 10, 12

## 2.3 Critério Todas-Arestas

0, 1, 2, 3, 2, 4, 5, 4, 6, 7, 1, 2, 4, 6, 1, 8, 9, 0, 1, 8, 9, 10, 11, 0, 1, 8, 10, 12

## 2.4 Critério Todos-Caminhos

0, 1, 2, 4, 6, 1, 8, 10, 12

0, 1, 2, 4, 6, 7, 1, 8, 9, 10, 12

0, 1, 2, 3, 2, 4, 5, 4, 6, 7, 1, 8, 9, 10, 11, 0, 1, 8, 9, 10, 12

0, 1, 2, 3, 2, 4, 5, 4, 6, 7, 1, 2, 4, 6, 1, 8, 9, 0, 1, 8, 9, 10, 11, 0, 1, 8, 10, 12

## Códigos JUnit

Não criei os códigos para o teste com JUnit, ainda preciso estudar sobre.