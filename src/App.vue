<script setup lang="ts">
import HomeView from "./pages/home-view.vue";
</script>

<template>
  <HomeView />
</template>

<style lang="scss">
  *{
    margin:0;
    padding:0;
    box-sizing:border-box;
  }

  body{
    background: #020208;
    background: linear-gradient(140deg, rgba(2, 2, 8, 1) 35%, rgba(184, 55, 0, 1) 100%);
    background-attachment:fixed;
  }

  section,
  .hero,
  .servicos,
  .container-sobre{
    background: transparent !important;
  }
</style>