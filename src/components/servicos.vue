<template>
    <section>
        <h2 class="titulo">Serviços</h2>
        <div class="container-servicos" data-aos="fade-up">
            <div class="container-servicos_container-fotos">
                <div v-if="categoriaAtiva === 'Sobrancelhas'"class="container-servicos_container-fotos_descricao">
                    <h6>Especialidade</h6>
                    <h4>Sobrancelha</h4>
                    <p>Design personalizado que realça a simetria e a harmonia natural do seu olhar.</p>
                </div>
                <div v-if="categoriaAtiva === 'Maquiagem'"class="container-servicos_container-fotos_descricao">
                    <h6>Especialidade</h6>
                    <h4>Sobrancelha</h4>
                    <p>Design personalizado que realça a simetria e a harmonia natural do seu olhar.</p>
                </div>
                <div v-if="categoriaAtiva === 'Henna'"class="container-servicos_container-fotos_descricao">
                    <h6>Especialidade</h6>
                    <h4>Sobrancelha</h4>
                    <p>Design personalizado que realça a simetria e a harmonia natural do seu olhar.</p>
                </div>
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
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
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
            height: 420px;
            width: 100%;
            margin: variaveis.$espacamentoTextos-md 0;
            @media(min-width:750px){
                flex-direction: row;
                max-width: 1062px;
            }

            &_container-fotos{
                width: 100%;
                height: 70%;
                position:relative;
                &_descricao{
                    display: flex;
                    justify-content: end;
                    flex-direction: column;
                    position: absolute;
                    bottom: 0;
                    left: 0;
                    width: 100%;
                    height: auto;
                    max-height: 50%;
                    z-index: 10;
                    padding: 0.75rem 1rem 1rem;
                    color:#fff;
                    background: linear-gradient(to top, rgba(0,0,0,0.8), rgba(0,0,0,0.2));
                    backdrop-filter: brightness(0.7);
                    -webkit-mask-image: linear-gradient(to top, rgba(0,0,0,1) 80%, rgba(0,0,0,0) 100%);
                    mask-image: linear-gradient(to top, rgba(0,0,0,1) 100%, rgba(0,0,0,0) 100%);

                    h6{
                        @include variaveis.fonteSubtilosImp;
                        font-size: 0.55rem;
                        letter-spacing: 0.15rem;
                        margin-bottom: 0.2rem;
                    }
                    h4{
                        @include variaveis.fontesPrincipais;
                        font-size: clamp(1.5rem, 6vw, 2.5rem);
                        line-height: 1;
                        margin-bottom: 0.35rem;
                    }
                    p{
                        @include variaveis.fonteParagrafos;
                        font-size: clamp(0.7rem, 2.8vw, 0.9rem);
                        line-height: 1.5;
                        max-width: 90%;
                    }

                    @media(min-width:750px){
                        height: 40%;
                        padding: variaveis.$espacamentoTextos-sm;

                        h6{
                            font-size: inherit;
                            margin-bottom: 0;
                        }

                        h4{
                            font-size: clamp(2rem, 2vw, 3rem);
                            margin-bottom: 0;
                        }

                        p{
                            max-width: 100%;
                            font-size: 1rem;
                        }
                    }
                }
                @media(min-width:750px){
                    width: 50%;
                    height: 100%;
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
                    height: 100%;
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