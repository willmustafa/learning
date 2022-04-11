---
layout: default
title: Outros Comandos
nav_order: 2
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