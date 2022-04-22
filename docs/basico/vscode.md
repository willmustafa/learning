---
layout: default
title: VsCode
nav_order: 1
parent: Básico
permalink: docs/basico/vscode
---

# Visual Studio Code

## Abrindo uma pasta com o terminal

Se estiver navegando pelo terminal e quiser abrir o vscode de toda a pasta, utilize:

```
code ./
```

## Criando Snippets

Você pode criar snippets pessoais para cada tipo de extensão (html, js, etc)

- `F1` -> snippets -> enter (para acessar `Preferences: Configure User Snippets`);
- Selecione a linguagem desejada para inserir o snippet ou crie um global;
- A estrutura é como a exibida no exemplo do vscode ou como abaixo:
  
```
    "Print to console": {
    "prefix": "log",
    "body": [
        "console.log('$1');",
        "$2"
    ],
    "description": "Log output to console"
    }
```

- Os campos que serão inseridos pelo usuário após a inserção do snippet é dado por $ e o número da ordem.
  
## Snippet não apareceu?

Caso o snippet não tenha aparecido, tente forçar com o atalho:

```
ctrl + espaço
```

## Atalhos Essenciais

### Criando estruturas html

Você pode estruturar um html com um simples texto como: 

`section>div.container>div.card>img.img-fluid+h5`

E isso irá gerar o seguinte código:

```
<section>
    <div class="container">
        <div class="card">
            <img src="" alt="" class="img-fluid">
            <h5></h5>
        </div>
    </div>
</section>
```