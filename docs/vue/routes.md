---
layout: default
title: Routes
nav_order: 3
parent: VUE.js
permalink: docs/vue/routes
---

# Routes

Rotas é a maneira de se criar as páginas usando VUE, por meio de um plugin, que tomará conta de implementar a url requisitada com o componente desejado.

## Instalação
```
// Para Vue 3
npm i vue-router@4
```

## Utilização

Crie um arquivo .JS dentro da pasta src/routes, ou qualquer outra maneira que desejar e inclua o seguinte código;

```
// Importa o plugin
import { createRouter, createWebHashHistory } from "vue-router"

// Importa os componentes principais das páginas
import HomeView from '../views/HomeView.vue'
import ContactView from '../views/ContactView.vue'

// Cria as rotas baseadas no path da url
const routes = [
    {path: '/', component: HomeView},
    {path: '/contact', component: ContactView}
]

// Cria a rota
const router = createRouter({
    history: createWebHashHistory(),
    routes
})

// Exporta para ser utilizado no main.js
export default router;
```

Agora importe o router no main.js e insira no vue:

```
import { createApp } from 'vue'
import App from './App.vue'
import router from './routes'

createApp(App)
    .use(router) // Especifica para utilizar as rotas
    .mount('#app')
```

## Transitions

Para fazer transições entre as páginas, o vue cria situações perfeitas, que permitem que a troca de página tenha uma animação da escolha do usuário, através de css, fazendo com que a experiência do usuário seja melhorada por ele não ver que a página foi recarregada.

```
<template>
  <main>
    <HomeHeader />


    // No vue 3 a transição é feita dessa maneira
    <router-view v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <component :is="Component" />
      </transition>
    </router-view>


  </main>
</template>

// CSS padrão para as transições
<style>
  .fade-enter-from,
  .fade-leave-to{
    opacity: 0;
  }

  .fade-enter-active,
  .fade-leave-active{
    transition: opacity 0.25s ease-out;
  }
</style>
```