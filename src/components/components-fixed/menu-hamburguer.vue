<template>
    <div class="container-menu">
        <div class="container-menu_head">
            <button>X</button>
        </div>
        <div class="container-menu_conteudo">
            <button v-for="botao in botoes">
                {{ botao }}
            </button>
        </div>
    </div>
</template>
<script setup lang="ts">
import {ref} from "vue";

    const botoes = ref(["Início","Serviços","Sobre","Local","Contato"])
    const emitir = defineEmits(["btn-clicado"])
</script>
<style lang="scss" scoped>
@use "../components-scss/variaveis.scss";

    .container-menu{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        position: fixed;
        top: 0;
        height: 100%;
        background-color: variaveis.$corPadraoCorpo(40, 35, 33, 0.95) !important; // Podes trocar por red se quiseres testar o vermelho vivo
        backdrop-filter: blur(1px);
        backdrop-filter: brightness(0.1);
        box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
        z-index: 100;
        width: 100%;
        padding:variaveis.$espacamentoTextos-lg;
        @media(min-width:750px){
            display: none;
        }
        &_head{
            display: flex;
            justify-content: flex-end;
            width: 100%;
            position: absolute;
            top: 50px;
            padding: 0 3rem;
        }
        &_conteudo{
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 450px;
            width: 100%;
            button{
                height: 100%;
                width: 100%;
                background: none;
                border: none;
                border-bottom: 1px solid #D2C4BA;
                color: #D2C4BA;
                padding:2rem;
            }
        }
    }

</style>