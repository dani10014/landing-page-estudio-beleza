<template>
    <section id="Serviços" class="secao-pagina">
        <h2 class="titulo">Serviços</h2>
        <div class="container-servicos" data-aos="fade-up">
            <div class="container-servicos_container-fotos">
                <div v-if="buscarSecao" class="container-servicos_container-fotos_descricao">
                    <h6>Especialidade</h6>
                    <h4>{{ buscarSecao.especialidade }}</h4>
                    <p>{{ buscarSecao.subtitulo }}</p>
                </div>
                <Transition name="fade" v-for="secao in categorias">
                    <img v-if="secao.especialidade === categoriaAtiva" :src="secao.imagem" id="foto-sonbrancelha" :alt="secao.alt">
                </Transition>
            </div>
            <div class="container-servicos_container-botoes">
                <button v-for="botao in categorias" @click="categoriaAtiva = botao.especialidade" :class="{ativo:categoriaAtiva === botao.especialidade}">
                    {{ botao.especialidade }}
                </button>
            </div>
        </div>
    </section>
</template>
<script setup lang="ts">
    import {computed, ref} from "vue";
    import imagemSobrancelha from "../assets/IMG-20261008-WA0006.jpg"
    import imagemMaquiagem from "../assets/IMG-20261013-WA0004.jpg"
    import imagemHenna from "../assets/IMG-20261008-WA0003.jpg"

    const categorias = [{especialidade:"Design sobrancelhas",subtitulo:"Valorize a sua beleza natural com traços precisos e harmoniosos.",imagem:imagemSobrancelha,alt:"Foto Design sobrancelha"},
                        {especialidade:"Maquiagem social",subtitulo:"Técnicas profissionais e acabamento perfeito para te destacar.",imagem:imagemMaquiagem,alt:"Foto imagem Maquiagem"},
                        {especialidade:"Design com henna",subtitulo:"Cor intensa e efeito harmônico que valoriza o formato do teu rosto.",imagem:imagemHenna,alt:"Foto design com com henna"}];

    const categoriaAtiva = ref("Design sobrancelhas")
    
    const buscarSecao = computed (()=>{
        return categorias.find(secao => secao.especialidade === categoriaAtiva.value)
    })
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
        height: 100vh;
        @media(min-width:750px){
            height: 600px;
            margin-bottom: 2rem;
        }
        .titulo{
            @include variaveis.fonteSubtilosImp;
            text-align: center;
            margin: variaveis.$espacamentoTextos-lg;
            color: #fff;
            border-bottom: 1px solid variaveis.$corParagrafos;
            width:200px;
        }
        .container-servicos{
            display: flex;
            flex-direction: column;
            height: 100%;
            width: 100%;
            margin: variaveis.$espacamentoTextos-md 0;
            @media(min-width:750px){
                flex-direction: row;
                max-width: 1062px;
            }

            &_container-fotos{
                width: 100%;
                height: 50%;
                aspect-ratio: 4 / 3;
                overflow: hidden;
                position:relative;
                @media(min-width:750px){
                    height: auto;
                }
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
                    background: linear-gradient(to top, rgba(0,0,0,0.9) 20%, rgba(0,0,0,0.3)); /* Fundo escuro uniforme */
                    backdrop-filter: brightness(0.7);
                    -webkit-mask-image: linear-gradient(to top, rgba(0,0,0,1) 20%, rgba(0,0,0,0) 100%);
                    mask-image: linear-gradient(to top, rgba(0,0,0,1) 70%, rgba(0,0,0,0) 100%);

                    h6{
                        @include variaveis.fonteSubtilosImp;
                        font-size: 0.55rem;
                        letter-spacing: 0.15rem;
                        margin-bottom: 0.5rem;
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
                            font-size: 0.7rem;
                            margin-bottom: 0.5rem;
                        }

                        h4{
                            font-size: clamp(2rem, 2vw, 3rem);
                            margin-bottom: 0.7rem;
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
                    aspect-ratio: auto;
                }
                img{
                    position: absolute;
                    inset: 0;
                    display: block;
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
                height: 50%;
                gap: 10px;
                @media(min-width:750px){
                    width: 50%;
                    height: 100%;
                }
                button{
                    @include variaveis.botoesCta;
                    height: 100%;
                    backdrop-filter: blur(1px);
                    @media(min-width:750px){
                        flex: 1;
                        min-height: 0;
                        height: auto;
                    }
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