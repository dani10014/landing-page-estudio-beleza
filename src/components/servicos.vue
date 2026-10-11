<template>
    <section>
        <h2 class="titulo">Serviços</h2>
        <div class="container-servicos" data-aos="fade-up">
            <div class="container-servicos_container-fotos">
                <Transition name="fade">
                    <img src="../assets/IMG-20261008-WA0006.jpg" v-if="categoriaAtiva === 'Sobrancelhas'" id="foto-sonbrancelha" alt="Foto Design sobrancelha">
                </Transition>
                <Transition name="fade">
                    <img src="../assets/images.jpeg" v-if="categoriaAtiva === 'Maquiagem'" id="foto-sonbrancelha" alt="Foto Design Maquiagem">
                </Transition>
                <Transition name="fade">
                    <img src="../assets/henna.jpeg" v-if="categoriaAtiva === 'Henna'" id="foto-sonbrancelha" alt="Foto Design Henna">
                </Transition>
            </div>
            <div class="container-servicos_container-botoes">
                <button v-for="botao in categorias" @click="categoriaAtiva = botao" :class="{ativo:categoriaAtiva === botao}">
                    {{ botao }}
                </button>
            </div>
        </div>
    </section>
</template>
<script setup lang="ts">
    import {ref} from "vue";

    const categorias = ["Sobrancelhas","Maquiagem","Henna",]
    const categoriaAtiva = ref("Sobrancelhas")

</script>
<style lang="scss" scoped>
@use "./components-scss/variaveis" as variaveis;
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
    section{
        .titulo{
            @include variaveis.fonteSubtilosImp;
            text-align: center;
            margin: variaveis.$espacamentoTextos-lg;
            color: #fff;
            border-bottom: 1px solid variaveis.$corParagrafos;
            
        }
        .container-servicos{
            display: flex;
            flex-direction: column;
            width: 100%;
            height: 400px;
            @media(min-width:750px){
                flex-direction: row;
            }
            &_container-fotos{
                width: 100%;
                height: 100%;
                @media(min-width:750px){
                    width: 50%;
                }
                img{
                    width: 100%;
                    height: 100%;
                    -webkit-mask-image: linear-gradient(to bottom, rgba(0,0,0,1) 70%, rgba(0,0,0,0) 100%);
                    mask-image: linear-gradient(to bottom, rgba(0,0,0,1) 70%, rgba(0,0,0,0) 100%);
                    object-fit: cover;
                    @media(min-width:750px){
                        -webkit-mask-image: linear-gradient(to right, rgba(0,0,0,1) 70%, rgba(0,0,0,0) 100%);
                        mask-image: linear-gradient(to right, rgba(0,0,0,1) 70%, rgba(0,0,0,0) 100%);
                        object-fit: cover;
                    }
                }
            }
            &_container-botoes{
                display: flex;
                align-items: center;
                flex-direction: column;
                width: 100%;
                @media(min-width:750px){
                    width: 50%;
                }
                button{
                    @include variaveis.botoesCta;
                    height: 100%;
                }
                .ativo{
                    opacity: 0.5;
                    background-color: #fff;
                    color: black;
                }
            }
        }
    }

</style>