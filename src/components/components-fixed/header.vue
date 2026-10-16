<template>
    <header>
        <div class="cabecalho" data-aos="fade-up" :class="{headerAtivo:headerMovido}">
            <img src="../../assets/logo.png" class="cabecalho_logo">
            <div class="botoes-cabecalho">
                <button v-for="botao in botoes" @click="irSecao(botao)" :class="{ativoBtn:categoriaEscolhida === botao}">
                    {{ botao }}
                </button>
            </div>
            <div class="btn-hamburguer" @click="ativarMenu">
                <i class="fa-solid fa-bars"></i>
            </div>
        </div>
    </header>
</template>
<script setup lang="ts">
    import {ref,onMounted, onUnmounted} from "vue";
    
    const headerMovido = ref(false);

    const botoes = ref(["Início","Serviços","Sobre","Local","Contato"])
    const categoriaEscolhida = ref("Início")
    const emitirAvisoMenu = defineEmits(["menuFoiAtivo"])
    const secaoAtiva = ref("inicio");

    const ativarMenu = ()=>{
        emitirAvisoMenu("menuFoiAtivo");
    }
    
    const irSecao = ((botao:string)=>{
        categoriaEscolhida.value = botao;
        secaoAtiva.value = botao;

        const idSecao = botao;
        const elemento = document.getElementById(idSecao);

        if(elemento){
            elemento?.scrollIntoView({behavior:"smooth"});
        }
    })
    const verificaSecao = ()=>{
        const secoes = document.querySelectorAll(".secao-pagina") as NodeListOf<HTMLElement>;
        const scrollPos = window.scrollY + 200;

        secoes.forEach((secao) =>{
            const topoSec = secao.offsetTop
            const altura = secao.offsetHeight;
            const id = secao.getAttribute("id")

            if(scrollPos >= topoSec && scrollPos < topoSec + altura){
                botoes.value.forEach((btn:string) => {
                    const idBtn = btn

                    if(idBtn === id){
                        categoriaEscolhida.value = id
                    }
                });
            }
        })

    }
    const verificaScrol = (() =>{
        if(window.scrollY > 50){
            headerMovido.value = true;
        }else{

            headerMovido.value = false;
        }
        verificaSecao();
    })

    onMounted (()=>{
        window.addEventListener("scroll",verificaScrol)
    })
    onUnmounted (()=>{
        window.removeEventListener("scroll",verificaScrol)
    })

</script>
<style lang="scss" scoped>
@use "../components-scss/variaveis" as variaveis;

header{
    position: fixed;
    z-index: 20;
    right: 0;
    top: 2rem;
    left: 2rem;
    right: 2rem;
}
    .cabecalho{
        display: flex;
        background-color: inherit;
        justify-content: space-between;
        transition: all 0.3s ease-in-out;
        height:60px;
        @media(min-width:750px){
            &.headerAtivo{
                background-color: variaveis.$corPadraoCorpo(40, 35, 33, 0.95) !important; // Podes trocar por red se quiseres testar o vermelho vivo
                backdrop-filter: blur(8px);
                box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
                height: 50px;
                border-radius: 10px;
            }
        }
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