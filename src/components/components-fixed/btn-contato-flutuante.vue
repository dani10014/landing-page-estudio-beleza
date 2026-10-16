<template>
    <div class="container-btn" data-aos="fade-up">
        <button class="container-btn_botao" @click="redirecionar">
            <img src="../../assets/WhatsApp_Logo_PNG_Sem_Fundo_Transparente.png">
        </button>
    </div>
</template>
<script setup lang="ts">
    const redirecionar = () =>{
        window.open("https://wa.me/5567992417712?text=Olá!%20Gostaria%20de%20agendar%20um%20horário.")
    }
</script>
<style lang="scss" scoped>
@use "../components-scss/variaveis.scss" as variaveis;

    .container-btn{
        position: fixed;
        right: 50px;
        bottom: 75px;
        z-index: 200;
        &_botao{
            background-color: inherit;
            height: 50px;
            width: 50px;
            border-radius: 50%;
            border: none;
            img{
                width: 100%;
                height: 100%;
            }
        }
    }
</style>