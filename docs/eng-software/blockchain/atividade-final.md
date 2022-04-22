---
layout: default
title: Atividade Final
nav_order: 3
parent: Blockchain
grand_parent: Engenharia de Software
---

# Blockchain - Atividade Final

Atividade final do curso de Engenharia de Software da UEL - módulo Software Baseado em Blockchain

Os códigos, screenshots e detalhes podem ser vistos nos README.md de cada atividade ou abaixo.

## Atividade 1

1- Configuração do Ganache

![](/learning/docs/eng-software/blockchain/resources/ganache-inicio.png)

2- Conectando via truffle
```
truffle console --network ganache
```

3- Armazenando as informações de contas do ganache

```
web3.eth.getAccounts((err,res) => { accounts = res })
```

![Contas do Ganache no Console](/learning/docs/eng-software/blockchain/resources/contas-ganache.png?raw=true)

 4- Compilando contratos
 ```
 migrate
 ```
 ![Migrate 1](/learning/docs/eng-software/blockchain/resources/migrate1.png?raw=true)
 ![Migrate 2](/learning/docs/eng-software/blockchain/resources/migrate2.png?raw=true)

 5- Definindo quantidade de Tokens e checando quantidade disponível
 ```
 LdnaToken.deployed().then(instance => { instance.approve(LdnaFaucet.address, 100) })

 // Quantidade disponível por conta
 LdnaToken.deployed().then(instance => { instance.balanceOf(accounts[0]).then(console.log)})
 LdnaToken.deployed().then(instance => { instance.balanceOf(accounts[1]).then(console.log)})
 LdnaToken.deployed().then(instance => { instance.balanceOf(accounts[2]).then(console.log)})
 ```
 ![Console - Contas](/learning/docs/eng-software/blockchain/resources/contas.png?raw=true)

 6- Efetuando transações para as contas e verificando balanço
 ```
 //Como foi definido o limite de 10 tokens por transação, foram realizadas 3 retiradas totalizando 25 LdnaTokens
 LdnaFaucet.deployed().then(instance => {instance.withdraw(10, {from:accounts[1]})})
 LdnaFaucet.deployed().then(instance => {instance.withdraw(10, {from:accounts[1]})})
 LdnaFaucet.deployed().then(instance => {instance.withdraw(5, {from:accounts[1]})})
 LdnaToken.deployed().then(instance => { instance.balanceOf(accounts[1]).then(console.log)})

 LdnaFaucet.deployed().then(instance => {instance.withdraw(10, {from:accounts[2]})})
 LdnaFaucet.deployed().then(instance => {instance.withdraw(10, {from:accounts[2]})})
 LdnaFaucet.deployed().then(instance => {instance.withdraw(5, {from:accounts[2]})})
 LdnaToken.deployed().then(instance => { instance.balanceOf(accounts[2]).then(console.log)})

 LdnaToken.deployed().then(instance => { instance.balanceOf(accounts[0]).then(console.log)})
 ```
 ![Transações de LdnaToken](/learning/docs/eng-software/blockchain/resources/transactions.png)


 # Atividade 2a - Calculadora

 Foi utilizado uma aplicação front-end para a realização do exercício 2.

 1- Instalação do repositório do truffle pet-shop
 ```
 truffle unbox pet-shop
 ```

 2- Contract Calculadora

 Ver o arquivo solidity [aqui](contracts/Calculadora.sol)

 3- Em uso

 Abaixo o site em estado inicial

 ![index.html](/learning/docs/eng-software/blockchain/resources/calculadora-inicio.png?raw=true)

 Requisição para o MetaMask

 ![metamask](/learning/docs/eng-software/blockchain/resources/calculadora-requisitado.png?raw=true)

 Transação no Ganache
 
 ![ganache](/learning/docs/eng-software/blockchain/resources/calculadora-ganache.png?raw=true)


 # Atividade 2b - Retornar endereço do criador do contrato

 Teste realizado na plataforma remix.ethereum.org/

 1- Retornando contract owner

 ![owner address](/learning/docs/eng-software/blockchain/resources/getowner.png?raw=true)


# Atividade 2c - PayTheOwner 1 wei

Executado no remix

![paytheowner](/learning/docs/eng-software/blockchain/resources/payTheOwner.png?raw=true)


# Atividade 2d - Calculadora 1wei

Executado no remix

![deploy](/learning/docs/eng-software/blockchain/resources/calculadora-1wei.png?raw=true)

Resultado da conta e envio de wei

![resultado](/learning/docs/eng-software/blockchain/resources/calculadora-1wei-resultado.png?raw=true)

# Atividade 2e - Texto para hash

Executado no remix

![texto teste e resultado](/learning/docs/eng-software/blockchain/resources/hashstring.png?raw=true)