---
layout: default
title: Dinamic Page Title
nav_order: 4
parent: VUE.js
grand_parent: Javascript
---

# Título de página dinâmico usando Routes

Para mudar o título da página usando routes para a criação dos nomes automaticamente, utilize o seguinte código.

```
// Em Routes, adicione a propriedade "meta"
const routes = [
    {
        path: '/',
        name: 'Home',
        component: Home,
        meta:{
            title: "Home"
        }
    },
    {
        path: '/about',
        name: 'About',
        component: About,
        meta:{
            title: "About"
        }
    }
]

router.beforeEach((to, from, next) => {
    document.title = `${to.meta.title}`;
    next();
})

```