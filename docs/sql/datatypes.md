---
layout: default
title: Data Types
nav_order: 3
parent: SQL
permalink: docs/sql/datatypes
---

# Data Types

A tipagem das colunas em um SQL é uma parte muito importante na estruturação do banco de dados, uma boa tipagem gera um banco mais leve, mais rápido e fácil de gerenciar.

Os data types podem não estar disponíveis dependendo do software do banco de dados, apesar de que a maioria dos tipos básicos sejam, cada banco pode possuir uma estrutura própria, com diversos tipos diferentes, por isso, leia a documentação própria de cada um.

## Numérico

|Data type |	Descrição |
|:--------|:---------------|
|BIT(size) | Um número bit que pode ir de 1 a 64.|
|TINYINT(size) | Um inteiro que vai de -128 a 127 caso tenha negativo ou de 0 a 255 se apenas positivo |
|BOOL | 0 = falso, outros números = positivo |
|SMALLINT(size) |	Um inteiro que vai de -32.768 a 32.767 ou de 0 a 65.535. |
|MEDIUMINT(size) |	Um inteiro que vai de -8.388.608 a 8.388.607 ou de 0 a 16.777.215. |
|INT(size) | 	Um inteiro que vai de -2.147.483.648 a 2.147.483.647 ou 0 a 4.294.967.295. |
|BIGINT(size) |	Um inteiro que vai de -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807 ou 0 a 18.446.744.073.709.551.615. |
|FLOAT(p) |	Um valor float. |
|DOUBLE(size, d) |	Um número decimal de digitos específicos. |
|DECIMAL(size, d) |	Um número decimal de digitos específicos. |