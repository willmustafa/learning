---
layout: default
title: Outros Comandos
nav_order: 3
parent: SQL
permalink: docs/sql/outroscomandos
---

# Como dar reset em uma coluna com auto increment?

```
ALTER TABLE tablename AUTO_INCREMENT = 1
*Esse comando pode não ser aceito no mysql porque ele não aceita mudar o auto increment para um valor menor do que o atual

SET @count = 0;
UPDATE `users` SET `users`.`id` = @count:= @count + 1;
```

# Arredondando um valor

Arredondando um select avg para 2 decimais:
```
SELECT ROUND( AVG(preco), 2) FROM tabela

```

## Pegar a média de valores

```
SELECT AVG(preco) FROM tabela
```

Isso retorna um valor completo, com vários decimais caso haja.