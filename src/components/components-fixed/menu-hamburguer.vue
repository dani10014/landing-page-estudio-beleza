<template>
    <div class="container-menu">
        <div class="container-menu_head">
            <button class="btn-fechar-menu" @click="fecharMenu"><i class="fa-solid fa-xmark"></i></button>
        </div>
        <div class="container-menu_conteudo">
            <button v-for="botao in botoes" @click="mudarSecao(botao)" :class="{ativo:props.secaoAtiva === botao}">
                {{ botao }}
            </button>
        </div>
    </div>
</template>
<script setup lang="ts">
import {ref} from "vue";

    const botoes = ref(["Início","Serviços","Local","Sobre","Contato"])
    const emitir = defineEmits(["btn-clicado","btn-fechar-menu"])
    const props = defineProps<{ secaoAtiva: string }>()

    const mudarSecao = (secao:string) =>{
        emitir("btn-clicado",secao);
    }
    const fecharMenu = () =>{
        emitir("btn-fechar-menu");
    }
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
            top: 25px;
            padding: 0 1.1rem;
            .btn-fechar-menu{
                padding: variaveis.$espacamentoTextos-sm;
                border: none;
                background-color: inherit;
                color: #fff;
                font-size: 2rem;
            }
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
                color: #d6ccc2;
                border: none;
                padding:2rem;
                &:hover{
                    opacity: 0.5;
                    background-color: #fff;
                    color: black;
                }
            }
            .ativo{
                border-bottom: 3px solid #fff !important ;
                width: 50%;
            }
        }
    }

</style>