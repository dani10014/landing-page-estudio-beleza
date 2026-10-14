<template>
    <header>
        <div class="cabecalho" data-aos="fade-up">
            <img src="../../assets/logo.png" class="cabecalho_logo">
            <div class="botoes-cabecalho">
                <button v-for="botao in botoes" @click="categoriaEscolhida = botao" :class="{ativoBtn:categoriaEscolhida === botao}">
                    {{ botao }}
                </button>
            </div>
            <div class="btn-hamburguer" @click="menuAtivo = !menuAtivo">
                <i class="fa-solid fa-bars"></i>
            </div>
        </div>
    </header>
</template>
<script setup lang="ts">
    import {ref} from "vue";
    
    const botoes = ref(["Início","Serviços","Sobre","Local","Contato"])
    const categoriaEscolhida = ref("Inicio")
    const menuAtivo = ref(false);
    
</script>
<style lang="scss" scoped>
@use "../components-scss/variaveis" as variaveis;


    .cabecalho{
        display: flex;
        top: 2rem;
        left: 2rem;
        right: 2rem;
        height: 70px;
        background-color: inherit;
        justify-content: space-between;
        position: fixed;
        z-index: 20;
        &_logo{
            width: 40px;
            object-fit: cover;
        }
        .botoes-cabecalho{
            display: none;
            align-items: center;
            gap: 10px;
            @media(min-width:750px){
                gap: 100px;
                display: flex;
            }
            button{
                background-color: inherit;
                border: none !important;
                color: #d6ccc2;
                @include variaveis.botoesCta;
            }
            .ativoBtn{
                border-bottom: 1px solid #fff !important;
                
            }
        }
        .btn-hamburguer{
            display: flex;
            align-items: center;
            color: #fff;
            font-size: 2rem;
            @media(min-width:750px){
                display: none;
            }
        }
        
    }
</style>