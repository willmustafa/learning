---
layout: default
title: SQL
nav_order: 5
has_children: true
permalink: docs/sql
---

# SQL

Bancos de dados utilizam a linguagem SQL (Standard Query Language) para fazer requisições, inserções, etc. Ela é uma linguagem declarativa e para muitos casos, o conhecimento básico é o suficiente, mas para grandes bancos, o conhecimento avançados de sua estruturação retornam uma maior eficiência de seu uso, tanto de performance quanto de espaço em disco.

O SQL é uma linguagem base, ou seja, dependendo do software de banco de dados utilizado, a sua implementação muda. Os bancos mais utilizados são: Oracle, MySQL, MariaDB, PostgreSQL, Microsoft SQL Server e Firebase.

## Modelo Relacional

Resumidamente, um banco de dados relacional armazena um dado relacionando a sua linha com uma coluna. Este modelo é aplicado pela maioria das aplicações e pelos softwares listados acima.

## Modelo Não-Relacional ou NoSQL

O banco de dados não é estruturado com diversas colunas e relacionamentos entre tabelas, mas uma estrutura como o JSON. Seu uso é mais específico.

## Meus projetos usando SQL

Aqui estão alguns repositórios que criei utilizando SQL:

### [Valor dos Produtos no Mercado - WebScrapping](https://github.com/willmustafa/ValorMercado-WebScraping)

Nesse projeto, o usuário passa uma série de produtos ou links de supermercados para fazer a coleta de dados. As informações coletadas são então destrinchadas e inseridas em um banco de dados PostgreSQL local, onde podem ser consultadas futuramente.