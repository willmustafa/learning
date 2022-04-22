---
layout: default
title: Atividade 1 - Planejamento de teste para um sistema
nav_order: 3
parent: Atividades da disciplina de teste de software
permalink: docs/eng-software/atividades/atividade-1
---

# Atividade 1

Aluno: Willian Felipe Mustafa
Disciplina: Teste de Software

## 1.1 Requisitos

Planejamento de teste para um sistema.

Tente contemplar o modelo em V (parcial em algumas fases)
- Escolha um sistema/programa
- Realize o plano de teste
- Descreva e/ou apresente os casos de uso
- Proponha os casos de teste
- Execute os casos de teste
- Avalie e apresente os resultados

## 1.2 Sistema

Máquina de café automática com dinheiro

A máquina de café/chá automática é disponibilizada em locais onde o público / clientes podem realizar a compra de diferentes tipos de café expresso e chás através da inserção de moedas e notas de reais e selecionando o produto desejado no painel.

## 1.3 Plano de teste

O sistema em questão será utilizado pelo público em geral de todos os níveis de conhecimento, devendo portanto, ser de fácil entendimento, ter opções de cancelamento, mensagens claras de falhas e executar o pedido com precisão.

### 1.3.1 Requisitos à serem testados e os casos de teste

A seguir estão delimitados os requisitos à serem testados e uma breve descrição:

| Requisito                      | Descrição                                                                                                                                                                                | Teste                                                                                                                                          |
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Tipo de moeda                  | A moeda e cédula inseridas devem ser em Reais                                                                                                                                            | Inserir moedas e cédulas em reais e em dólar para verificar o aceite da máquina                                                                |
| Quantidade correta de dinheiro | Só é validado o pedido se a quantidade de dinheiro inserida for maior ou igual ao preço da bebida escolhida                                                                              | Inserir moedas em reais necessária e verificar o aceite                                                                                        |
| Troco                          | Se o valor inserido for maior que o necessário, a máquina deve retornar o valor excedente e caso não tenha o valor do troco, impeça a fabricação da bebida e devolva o dinheiro inserido | Inserir mais dinheiro que o disponível na máquina e tentar fazer uma compra, verificar se é retornado o troco correto ou impedimento da compra |
| Fabricação da bebida           | A bebida escolhida foi executada conforme requisitada?                                                                                                                                   | Verificar se a seleção da bebida e a fabricação estão corretos                                                                                 |

### 1.3.2 Casos de uso

Caso de uso para um cliente:

- Cliente seleciona a bebida desejada (ex: café curto)
- O valor da bebida aparece no display (ex: R$ 1,50)
- O cliente insere uma cédula de dinheiro (ex: R$ 2,00)
- A máquina retorna o troco (ex: R$ 0,50)
- A máquina fabrica a bebida
- A máquina entrega a bebida
- O display retorna ao estado inicial

Caso de uso para o responsável pela máquina:

- O responsável digita a senha no display
- A máquina destranca o compartimento interno
- O responsável verifica a quantidade de produtos e de dinheiro
- O responsável faz o reabastecimento e fecha a máquina
- A máquina tranca o compartimento interno
- A máquina faz a verificação dos produtos e dinheiro disponíveis
- O display retorna ao estado inicial

### 1.3.3 Execução dos testes

A execução de caixa preta será realizada pela equipe de qualidade conforme descrito no item 1.3.1.

### 1.3.4 Avaliação dos testes

Gerar relatório da execução dos testes e os devidos retornos.