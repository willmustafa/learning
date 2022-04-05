---
layout: default
title: VUE.js
nav_order: 5
has_children: true
permalink: docs/vue
---

# VUE.js

O Vue (pronunciado igual view) é um framework de JavaScript para construir a interface de usuário.

>Renderização Declarativa: Vue adiciona a sintaxe "template" ao HTML, permitindo que permite que o HTML seja declarado conforme o estado de um JavaScript.
>Reatividade: Vue rastreia automaticamente as alterações de estado do Javascript e atualiza com eficiência o DOM quando há alterações.

No Vue, os arquivos são Single-File Components, ou seja, a lógica do componente é toda empregada em um único arquivo, da seguinte forma:

```
// JavaScript
<script>
export default {
  data() {
    return {
      count: 0
    }
  }
}
</script>

// HTML
<template>
  <button @click="count++">Count is: {{ count }}</button>
</template>

// CSS
<style scoped>
button {
  font-weight: bold;
}
</style>
```

## Como funciona?

No vue, o arquivo index.html não possui toda sua estrutura, a parte interna do site se encontra na pasta ```src```.

Todos os arquivos da pasta src são transformados em um bundle chamado build.js e este é carregado pelo index.html.

Dentro do arquivo ```App.vue``` todo o código dentro da tag ```<template>``` deve ser colocada dentro de uma única ```<div>``` ou outro elemento.


## Passando informações

No ```<script>``` do App.vue, você pode passar informações que serão acessadas pela página atual:

```
<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>
```

Com o código acima, o parâmetro msg pode ser acessado utilizando a notação {{ msg }}.

Mas quando esse parâmetro é passado para dentro de um atributo como o link de uma imagem, ele precisa ser escrito da seguinte forma:

```
<img :src="msg">
ou
<img v-bind:src="msg">
```

### Passando uma array

Caso tenham vários dados com parâmetros repetidos como a exibição de produtos em uma home, o VUE possui maneiras de iterar informações passadas como array, utilizando ```v-for="x of properties"``` ou ```v-for="x in properties"```:

```
<ul>
    <li v-for="blog of bloginfo">
        <h3>blog.titulo</h3>
        <img :src="blog.thumb" :alt="blog.thumb-text">
    </li>
</ul>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      title: 'Blog Posts',
      bloginfo: [
          {
              titulo: '747-800',
              thumb: 'link-747-800.jpg',
              thumb-text: 'avião 747-800'
          },
          {
              titulo: '777-800',
              thumb: 'link-777-800.jpg',
              thumb-text: 'avião 777-800'
          }
      ]

    }
  }
}
</script>
```

### Requisições para uma API usando Vue-resource

Para fazer requisições para apis, ao invez de utilizar um comando fetch, usamos o pacote vue-resource.

```
npm install vue-resource

import VueResource from 'vue-resource'

// usando globalmente
Vue.use(VueResource)
```

Utilizando o comando $http para acessar uma página;

```
// Dentro do componente vue export default
created () {
    this.$http.get('http://localhost:3000/v1/fotos')
      .then(res => res.json())
      .then(fotos => this.fotos = fotos, err => console.log(err))
  }
// Esse comando faz a leitura do get como promisse, e faz o retorno desejado
```

### Estilos

Os styles de um componente são carregados juntos do próprio componente vue e são carregados direto na head da html quando invocadas.

Para restringir o estilo ao componente, adicione scoped na tag style ```<style scoped>```

## Componentes

Os shared components são partes de códigos que podem ser reutilizados na aplicação.

Quando chamar um componente, será necessário importa-lo no script.

Para passar uma propriedade para esse componente, ele precisa primeiro aceitar esse parâmetro.

```
// :titulo passará informações para o componente
<meu-painel :titulo="foto.titulo">
    <img src="foto.jpg"> // Será exibido dentro da tag "slot" do componente
</meu-painel>

import Painel from './components/painel.vue'

export default {
    components: {
        'meu-painel': Painel
    }
}

// no componente
<template>
    <div>
        <h1>{{ titulo }}</h1>
        <slot class="algo">
        </slot>
    </div>
</template>

export default {
    props: ['titulo']
}
```

Você também pode criar slots nomeados
```
<!-- ComponenteQualquer.vue -->
<template>
    <div>
        <slot name="cabecalho" class="header" ></slot>
        <hr>
        <slot class="body"></slot>
        <hr>
        <slot name="rodape" class="footer"></slot>
    </div>
</template>
<script>
export default {}
</script>

<componente-qualquer>
    <div slot="cabecalho">
        <h1>Bem-vindo!</h1>
    </div>
    <p>Seja bem-vindo à Alura!</p>
    <div slot="rodape">
        <p>copyright 2017</p>
    </div>
</componente-qualquer>
```

## Eventos

```
<input v-on:input="filtro = $event.target.value">
// ou @
<input @input="filtro = $event.target.value">

export default {
    data () {
        filtro: ''
    }
}
```

Um dado pode ser puxado através de uma fórmula que é passada dentro do script export, como por exemplo quando um dado precisa ser filtrado antes de ser iterado em um loop.

```
<h1>{{ fotosComFiltro }}</h1>

export default {
    computed: {
        fotosComFiltro () {
            if(this.filtro) {
                return []
            } else {
                return this.fotos
            }
        }
    }
}
```
## Transition

```
<!-- alurapic/src/componets/shared/painel/Painel.vue -->

<template>

  <div class="painel">

    <h2 class="painel-titulo" @dblclick="visivel = !visivel">{{ titulo }}</h2>
    <transition name="painel-fade">
      <div class="painel-conteudo" v-show="visivel">
        <slot></slot>
      </div>
    </transition>

  </div>

</template>

<script>
// código omitido 
</script>

<style>
 /* código anterior omitido */

.painel-fade-enter, .painel-fade-leave-active {
  opacity: 0
}

.painel-fade-enter-active, .painel-fade-leave-active {
  transition: opacity .4s
}
</style>
```


## Métodos

As funções podem ser chamadas através de methods dentro do vue.