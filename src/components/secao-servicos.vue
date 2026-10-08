<template>
    <div class="container-servicos">
        <div class="container-servicos_imagens-fundo">
            <img data-aos="fade-up" src="../assets/IMG-20261008-WA0003.jpg">
            <img data-aos="fade-up" src="../assets/IMG-20261008-WA0005.jpg">
            <img data-aos="fade-up" src="../assets/IMG-20261008-WA0006.jpg">
        </div>
        <div class="titulo">
            <h2>Serviços</h2>
        </div>
    </div>
</template>
<script setup lang="ts">

</script>
<style lang="scss" scoped>
@use "../component-scss/variaveis.scss";
    .container-servicos{
        height: 100vh;
        position:relative;
        &_imagens-fundo{
            position:absolute;
            top: 0;
            height:100%;
            z-index:-1;
            display:flex;
            flex-direction:column;
            img{
                width:100%;
                height:100%;
                object-fit:cover;
            }
        }
    }

</style>