<template>
    <section>
    <div class="container-sobre">
        <h2>Sobre mim</h2>
        <div class="container-sobre_imagem-profissional">
            <img src="../assets/IMG-20261008-WA0006.jpg">
        </div>
        <div class="container-sobre_nome-e-especializacao">
            
        </div>
    </div>
    </section>
</template>
<script setup lang="ts">

</script>
<style lang="scss" scoped>
@use "../component-scss/variaveis.scss";
    section{
        background: #f8f6f2;
    }
    .container-sobre{
        display: flex;
        flex-direction: column;
        height: 100vh;
        width:100%;
        background: #f8f6f2;
        color: #252b27;
        position: relative;
        max-width: 1160px;
        margin: 0 auto;
        h2{
            margin:2rem variaveis.$margenSite;
            border-bottom: 1px solid #d9ded8;
            font-family: "Playfair Display", serif;
            font-size: clamp(2.5rem, 8vw, 4rem);
            font-weight: 600;
            line-height: 1.1;
        }
        &_imagem-profissional{
            display: flex;
            justify-content: center;
            width: 100%;
            height: 200px;
            position: absolute;
            top: 100px;
            img{
                width: 50%;
                height: 100%;
                border-radius: 50%;
                border: 2px solid #252b27;
                box-shadow: 0px 0px 5px black;
                @media(min-width:750px){
                    width: 20%;
                }
            }
        }
        &_nome-e-especializacao{
            display: flex;
            flex-direction: column;
            height: 100%;
            background-color: #f8f6f2;;
            margin-top: 10rem;
            margin:10rem variaveis.$margenSite;
            border-top-left-radius:10px ;
            border-top-right-radius:10px ;
            @media(min-width:750px){
                height: 70%;
            }
        }
    }

</style>