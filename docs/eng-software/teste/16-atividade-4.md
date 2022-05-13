---
layout: default
title: Atividade 4 - Teste Baseado em Modelo
nav_order: 16
parent: Teste de Software
grand_parent: Engenharia de Software
---

# Atividade 4 - Teste Baseado em Modelo

Aluno: Willian Felipe Mustafa

Disciplina: Teste de Software

## 1.1 Descrição do Problema

Escolha um sistema
- Modele usando IOLTS (o foco são os eventos e o fluxo)
- Gere os testes usando a Everest
- Projete em torno de duas IUTs (corretas e com falhas, ao menos)
- Execute os testes
- Apresente os resultados

# 2.0 Sistema escolhido

Será utilizado uma máquina de café/chá conforme na atividade 1.

Máquina de café automática com dinheiro

![](https://www.newchang.com.br/newchang/opera.png)

A máquina de café/chá automática é disponibilizada em locais onde o público / clientes podem realizar a compra de diferentes tipos de café expresso e chás através da inserção de moedas e notas de reais e selecionando o produto desejado no painel.

Para essa atividade, as saídas possíveis para a máquina serão:

- Café curto
- Cappuccino
- Chá verde

As entradas possíveis serão:

- Botão que seleciona cada bebida
- Botão de cancelamento
- Cédulas de dinheiro de 2, 5 ou 10 reais

## 2.1 IOLTS

Conforme dito anteriormente, teremos Li (entrada) e Lu (saída) como a seguir:

Li = {e1, e2, e3, x, n}

Lu = {cc, cp, cv, d}

Onde:

e1 = Escolha da bebida 1 (Café curto);
e2 = Escolha da bebida 2 (Cappuccino);
e3 = Escolha da bebida 3 (Chá verde);
no = Botão de cancelamento;
ye = Botão de produzir;
n = Valor em reais inseridos;
cc = Café curto;
cp = Cappuccino;
cv = Chá verde;
d = Devolução do dinheiro.

```
des (s0,20,4) 
(s0,?e1,s1) // Escolhido botão 1
(s1,?n,s2) // Inserido o valor requerido
(s2,?ye,s3) // Escolha de produzir o café
(s2,?no,s4) // Escolha de cancelar
(s4,!d,s0) // Devolve o dinheiro e retorna ao estado inicial
(s3,!cc,s0) // Gera o café e volta ao estado inicial

(s0,?e2,s5) // Escolhido botão 2
(s5,?n,s6) // Inserido o valor requerido
(s6,?ye,s7) // Escolha de produzir o cappuccino
(s6,?no,s4) // Escolha de cancelar
(s4,!d,s0) // Devolve o dinheiro e retorna ao estado inicial
(s7,!cp,s0) // Gera o cappuccino e volta ao estado inicial

(s0,?e3,s8) // Escolhido botão 3
(s8,?n,s9) // Inserido o valor requerido
(s9,?ye,s10) // Escolha de produzir o chá
(s9,?no,s4) // Escolha de cancelar
(s4,!d,s0) // Devolve o dinheiro e retorna ao estado inicial
(s3,!cv,s0) // Gera o chá e volta ao estado inicial
```

![](/learning/docs/eng-software/teste/resources/iolt.png?raw=true)


## 2.2 Geração de testes pelo everest

```
des(s0_0,17,3)
(s0_0,!d,fail)
(s0_0,?no,pass)
(s0_0,?e1,pass)
(s0_0,?ye,pass)
(s0_0,?e2,pass)
(s0_0,?n,pass)
(s0_0,?e3,pass)
(pass,!cc,pass)
(fail,!cc,fail)
(pass,!cv,pass)
(fail,!cv,fail)
(pass,!d,pass)
(fail,!d,fail)
(pass,delta,pass)
(fail,delta,fail)
(pass,!cp,pass)
(fail,!cp,fail)
```

```
des(s0_0,17,3)
(s0_0,!d,fail)
(s0_0,?no,pass)
(s0_0,?e1,pass)
(s0_0,?ye,pass)
(s0_0,?e2,pass)
(s0_0,?n,pass)
(s0_0,?e3,pass)
(pass,!cc,pass)
(fail,!cc,fail)
(pass,!cv,pass)
(fail,!cv,fail)
(pass,!d,pass)
(fail,!d,fail)
(pass,delta,pass)
(fail,delta,fail)
(pass,!cp,pass)
(fail,!cp,fail)
```

## 2.3 Resultados

```
Test case: 	

Model outputs: [δ] 

	 path:s0
	 output: [δ]

Implementation outputs: [d] 

	 path: s0_0
	 output: [d]

################################################################## 
Test case: 	e1

Model outputs: [δ] 

	 path:s0 -> s1
	 output: [δ]


Implementation outputs: [cc, cv, d, δ, cp] 
 
	 path:s0_0 -> pass
	 output: [cc, cv, d, δ, cp]


################################################################## 
Test case: 	e2

Model outputs: [δ] 

	 path:s0 -> s5
	 output: [δ]


Implementation outputs: [cc, cv, d, δ, cp] 
 
	 path:s0_0 -> pass
	 output: [cc, cv, d, δ, cp]


################################################################## 
Test case: 	e3

Model outputs: [δ] 

	 path:s0 -> s8
	 output: [δ]


Implementation outputs: [cc, cv, d, δ, cp] 
 
	 path:s0_0 -> pass
	 output: [cc, cv, d, δ, cp]


################################################################## 


```

```
Test case: 	

Model outputs: [δ] 

	 path:s0
	 output: [δ]

Implementation outputs: [d] 

	 path: s0_0
	 output: [d]

################################################################## 
Test case: 	e1

Model outputs: [δ] 

	 path:s0 -> s1
	 output: [δ]


Implementation outputs: [cc, cv, d, δ, cp] 
 
	 path:s0_0 -> pass
	 output: [cc, cv, d, δ, cp]


################################################################## 
Test case: 	e2

Model outputs: [δ] 

	 path:s0 -> s5
	 output: [δ]


Implementation outputs: [cc, cv, d, δ, cp] 
 
	 path:s0_0 -> pass
	 output: [cc, cv, d, δ, cp]


################################################################## 
Test case: 	e3

Model outputs: [δ] 

	 path:s0 -> s8
	 output: [δ]


Implementation outputs: [cc, cv, d, δ, cp] 
 
	 path:s0_0 -> pass
	 output: [cc, cv, d, δ, cp]


################################################################## 

```