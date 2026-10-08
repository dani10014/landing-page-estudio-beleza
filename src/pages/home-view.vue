<template>
    <Header @menu-ativo="ativarMenu"/>
    <HomeView/>
    <secaoServicos/>
    <secaoSobreMim/>
    <Transition name="fade">
        <Menu v-if="menuAtivo"/>
    </Transition>
</template>
<script setup lang="ts">
    import HomeView from "../components/heroSection.vue";
    import secaoServicos from "../components/secao-servicos.vue";
    import secaoSobreMim from "../components/secao-sobre-mim.vue";
    import Header from "../components/header.vue";
    import Menu from "../components/menu.vue";
    import {ref} from "vue";

    const menuAtivo = ref(false);

    const ativarMenu = () =>{
        menuAtivo.value = !menuAtivo.value;
    }

</script>
<style lang="scss">
    .fade-enter-active,
    .fade-leave-active {
        transition: opacity 0.4s ease;
    }

    .fade-enter-from,
    .fade-leave-to {
        opacity: 0;
    }
</style>