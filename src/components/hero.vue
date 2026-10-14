<template>
    <section>
        <div class="container-texto-hero" data-aos="fade-up">
            <h1 class="container-texto-hero_nome-salao">Liz Aquino</h1>
            <p class="container-texto-hero_servico">Espaço de beleza</p>
            <p class="container-texto-hero_localizacao"> Bonito - MS <i class="fa-solid fa-map"></i> </p>
            <h3 class="container-texto-hero_texto-incentivo">Realce o que te faz única</h3>
            <button class="btn-CTA" @click="redirecionar">Agendar <i class="fa-solid fa-calendar-days" id="icone-agendar"></i></button>
        </div>
    </section>
</template>
<script setup lang="ts">

    const redirecionar = () =>{
        window.open("https://wa.me/5567992417712?text=Olá!%20Gostaria%20de%20agendar%20um%20horário.")
    }

</script>
<style lang="scss" scoped>
@use "./components-scss/variaveis" as variaveis;

section{
    display: flex;
    justify-content: center;
    height: 100vh;
    
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
        @include variaveis.fonteSubtilosImp;
    }
    &_localizacao{
        border-bottom: 1px solid #d6ccc2;
        margin:variaveis.$espacamentoTextos-md 0;
        color:#d6ccc2 ;
        i{
            margin-left: 0.5rem;
        }
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
        #icone-agendar{
            margin-left: 1rem;
        }
        @media(min-width:750px){
            width: 50%;
        }
    }
}
</style>