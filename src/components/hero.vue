<template>
    <section>
        <div class="container-texto-hero" data-aos="fade-up">
            <h1 class="container-texto-hero_nome-salao">Liz Aquino</h1>
            <p class="container-texto-hero_servico">Espaço de beleza</p>
            <h3 class="container-texto-hero_texto-incentivo">Realçe toda a beleza que habita em você</h3>
            <button class="btn-CTA">Agendar</button>
        </div>
    </section>
</template>
<script setup lang="ts">

</script>
<style lang="scss" scoped>
@use "./components-scss/variaveis" as variaveis;

section{
    display: flex;
    justify-content: center;
    height: 100%;
    
}
.container-texto-hero{
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    text-align: center;
    width: 100%;
    @media(min-width:750px){
        text-align: start;
        max-width: 1062px;
        align-items: flex-start;
    }
    &_nome-salao{
        @include variaveis.fontesPrincipais;
        color: #d6ccc2;
    }
    &_servico{
        color:variaveis.$corParagrafos;
        margin-bottom: variaveis.$espacamentoTextos-lg;
        @include variaveis.fonteSubtilosImp;
    }
    &_texto-incentivo{
        color: variaveis.$corParagrafos;
        margin-bottom: variaveis.$espacamentoTextos-md;
        @include variaveis.fonteParagrafos;
    }
    .btn-CTA{
        padding: variaveis.$espacamentoTextos-sm;
        width: 100%;
        border: none;
        background: none;
        border: 1px solid #fff;
        color: #fff;
        transition: all 0.3s ease-in-out;
        text-transform: uppercase;
        &:hover{
            opacity: 0.5;
            background-color: #fff;
            color: black;

        }
        @media(min-width:750px){
            width: 50%;
        }
    }
}
</style>