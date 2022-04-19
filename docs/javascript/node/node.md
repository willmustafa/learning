---
layout: default
title: Node
nav_order: 4
has_children: true
permalink: docs/javascript/node
---

# Node.js

# Iniciando um novo projeto

```
npm init
```

## Mostrando o progresso no console

Um bom pacote para adicionar comandos de progresso é o [progress](https://www.npmjs.com/package/progress).

```
var ProgressBar = require('progress');
 
var bar = new ProgressBar(':bar', { total: 10 });
var timer = setInterval(function () {
  bar.tick();
  if (bar.complete) {
    console.log('\ncomplete\n');
    clearInterval(timer);
  }
}, 100);
```

## Escrevendo arquivos

Uma forma de criar arquivos é usando `fs.writeFileSync`:

```
fs.writeFileSync(filePath, JSON.stringify(data))
```