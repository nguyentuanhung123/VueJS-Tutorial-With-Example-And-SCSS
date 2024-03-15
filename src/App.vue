<template>
  <div class="app">
    <Sidebar />
    <router-view />
  </div>
</template>

<script setup>
  import Sidebar from './components/Sidebar.vue';
</script>

<style lang="scss">
.app {
  display: flex;

  main {
    flex: 1 1 0;
    padding: 2rem;

    @media (max-width: 768px){
      padding-left: 6rem;
    }
  }
}
</style>


