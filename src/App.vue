<script setup lang="ts">
import Hero from './components/hero.vue'
import Header from "./components/components-fixed/header.vue"
import Servicos from "./components/servicos.vue";
import menuHamburguer from './components/components-fixed/menu-hamburguer.vue';
import {ref} from "vue";

  const menuAtivo = ref(false);

  const ativarMenu = ()=>{
    menuAtivo.value = !menuAtivo.value
  }
</script>
<template>
  <Transition name="fade">
      <menuHamburguer v-if="menuAtivo"/>
  </Transition>
  <div class="divisor-background" >

  </div>
  <div class="landing-container">
    <Header @menuFoiAtivo="ativarMenu"/>
    <Hero/>
    <Servicos/>
  </div>
</template>
<style lang="scss">
    *{
      padding:0;
      margin:0;
      box-sizing: border-box;
    }
    body{
      background-color: #675A4F;
    }
    .fade-enter-active,
    .fade-leave-active {
        transition: opacity 0.4s ease, transform 0.4s ease;
    }

    .fade-enter-from {
        opacity: 0;
        transform: scale(1.02); /* Dá um zoom subtil ao entrar */
    }

    .fade-leave-to {
        opacity: 0;
    }
    .landing-container{
      padding:2rem;
      position: relative;
      height: 100vh;
    }
    .divisor-background{
        background-image: url("./assets/IMG-20261008-WA0011.jpg");
        background-position: center;
        background-size: cover;
        position: absolute;
        right: 0;
        top: 0;
        height: 100%;
        bottom: 30px;
        width: 100%;
        z-index: -1;
        filter: brightness(0.5);
        -webkit-mask-image: linear-gradient(to bottom, rgba(0,0,0,1) 70%, rgba(0,0,0,0) 100%);
        mask-image: linear-gradient(to bottom, rgba(0,0,0,1) 70%, rgba(0,0,0,0) 100%);
        @media(min-width:750px){
          width: 50%;
          -webkit-mask-image: linear-gradient(to left, rgba(0,0,0,1) 70%, rgba(0,0,0,0) 100%);
          mask-image: linear-gradient(to left, rgba(0,0,0,1) 70%, rgba(0,0,0,0) 100%);
          filter: brightness(1);
        }
      }
</style>