# Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Add Icon to Vue

B1 : https://github.com/google/material-design-icons
B2 : Copy <link href="https://fonts.googleapis.com/css2?family=Material+Icons" rel="stylesheet">
B3 : Page vào index.html dưới title

## Dùng Google Fonts

B1 : Vào https://fonts.google.com/
B2 : Thêm các kiểu chữ như bình thường ví dung: fira
B3 : Ấn vào biểu tưởng giống túi xách ở bên phải màn hình (View selected families)
B4 : Nhấn vào button Get Embed Code
B5 : Copy 3 thẻ Link đang được hiện ra (ở radio link)
B6 : Page vào index.html dưới title
B7 : Vào style.css
\*{
margin: 0;
padding: 0;
box-sizing: border-box;
font-family: 'Fira sans', sans-serif;
}

## Dùng Sas

npm i -D sass

## Dùng router

B1 : npm i vue-router
B2 : Vào main.js
import { createRouter, createWebHistory } from 'vue-router'
import Home from './views/Home.vue'

const router = createRouter({
history: createWebHistory(),
routes: [
{
path: '/',
component: () => Home
},
{
path: '/about',
component: () => import ('./views/About.vue')
},

    ]

})  
B3: Sửa createApp(App).mount('#app') => createApp(App).use(router).mount('#app')
B4: Sửa trong App.vue

<h1>Hello, World!</h1> -> <router-view />
B5: Tạo thư mục mới : router trong thư mục src
B6: Tạo file index.js trong thư mục router
B7 : Copy đoạn code và xoá nó đi trong file main.js
import { createRouter, createWebHistory } from 'vue-router'
import Home from './views/Home.vue'

const router = createRouter({
history: createWebHistory(),
routes: [
{
path: '/',
component: () => Home
},
{
path: '/about',
component: () => import ('./views/About.vue')
},

    ]

})  
B8: Paste vào index.js vừa tạo
B9: Sửa
import Home from './views/Home.vue' -> import Home from '../views/Home.vue'
component: () => import ('./views/About.vue') -> import ('../views/About.vue')
B10: Bổ sung bên dưới :
export default router
B11: import router from './router' trong main.js

## Các bước chuẩn bị

B1 : Xoá component HelloWorld.vue
B2 : Vào App.vue và xoá đường dẫn import của HelloWorld.vue
import HelloWorld from './components/HelloWorld.vue'
<HelloWorld msg="Vite + Vue" />
B3 : Xoá hết các css ở style trong App.vue và thay thế bằng scss

<style Lang="scss">

</style>

B4 : Xoá hoặc comment import './style.css' trong main.js
B5 : Xoá hết ở App.vue chỉ để lại

<script setup>
</script>

<template>
  <div class="app">
    <h1>Hello World</h1>
  </div>
</template>

<style Lang="scss">

</style>
