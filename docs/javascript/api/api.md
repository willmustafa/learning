---
layout: default
title: Api
nav_order: 4
has_children: true
parent: Javascript
---

# API RESTFul

Uma API REST é uma interface de programação de aplicações, não é um protocolo ou padrão, mas um conjunto de restrições de arquitetura.


## Criando uma API com Express

Importando o pacote:

```
npm i express body-parser
```

Iniciando o express e as rotas:

```
const express = require('express')
const bodyParser = require('body-parser')
const app = express()

app.use('/', require('./route/routes'))

// MIDDLEWARES
app.use(bodyParser.json());

app.listen(3000)
```

Arquivo de rotas:

```
const express = require('express')
const router = express.Router()

const historicoData = require('../data/historicoData')

router.get('/historico', async function (req, res) {
    res.json(await historicoData.getHistorico(req.query))
})

router.get('/historico/media', async function (req, res) {
    res.json(await historicoData.getMedia(req.query))
})

module.exports = router
```

Aqui você pode gerar varios arquivos separados que irão solucionar partes específicas das rotas.