<template>
    <div class="hero">
        <div class="hero_hero-image">
            <img src="../assets/IMG-20261008-WA0017.jpg" alt="imagem hero  - foto profissional Liz Aquino" />
        </div>
        <div class="hero_hero-apresentacao">
            <h1 data-aos="fade-up">Liz Aquino</h1>
            <h4 data-aos="fade-up">Espaço de beleza</h4>
            <p data-aos="fade-up">Bonito - MS  <i class="fa-solid fa-location-dot"></i></p>
            <div class="btn-agendar" data-aos="fade-up">
                <button>Agendar</button>
            </div>
        </div>
    </div>
</template>
<script setup lang="ts">

</script>
<style lang="scss" scoped>
@use "../component-scss/variaveis.scss";

    .hero{
        display:flex;
        justify-content:center;
        height:100vh;
        position:relative;
        z-index:-1;
        padding:0 variaveis.$margenSite;
        overflow:hidden;
        &_hero-image{
            position:absolute;
            height:100%;
            width:100%;
            filter: brightness(0.3);
            img{
                height:100%;
                width:100%;
                object-fit:cover;
                object-position:center;
            }
        }
        &_hero-apresentacao{
            position:absolute;
            bottom:20%;
            color:white;
            text-align:center;
            @media (min-width:750px){
                bottom:20%;
            }
            h1{
                @include variaveis.fonteTitulosPrincipais;
                @media(min-width:750px){
                    font-size:4rem
                }
            }
            h4{
                @include variaveis.subtitulos;
                margin-bottom:2rem;
                @media(min-width:750px){
                    font-size:1rem;
                }
            }
            p{
                margin:2rem 0;
                
                @media(min-width:750px){
                    font-size:1rem;
                    margin:3rem 0;
                }
            }
            .btn-agendar{
                margin-top:2rem;
                button{
                    background-color:#fff;
                    color:black;
                    border:1px solid white;
                    padding:0.7rem 1rem;
                    width:100%;
                    font-size:1rem;
                    cursor:pointer;
                    transition:all 0.3s ease-in-out;
                    border-radius:0.5rem;
                    @include variaveis.fonteBotoes;
                }
            }
        }
    }
</style>