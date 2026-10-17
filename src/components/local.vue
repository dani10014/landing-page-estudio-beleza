<template>
    <section id="Local" class="secao-pagina">
        <h2 class="titulo">Local</h2>
        <div class="container-local">
            <div class="container-local_div1">
                <img src="../assets/IMG-20261008-WA0018.jpg"></img>
            </div>
            <div class="container-local_div1">
                
            </div>
            <div class="container-local_container-informacao">

            </div>
        </div>
    </section>
</template>
<script setup lang="ts">

</script>
<style lang="scss" scoped>
@use "./components-scss/variaveis" as variaveis;

section{
    display: flex;
    justify-content: center;

    align-items: center;
    flex-direction: column;
    height: 100vh;
    .titulo{
        @include variaveis.fonteSubtilosImp;
        text-align: center;
        margin: variaveis.$espacamentoTextos-lg;
        color: #fff;
        border-bottom: 1px solid variaveis.$corParagrafos;
    } 
    .container-local{
        display: flex;
        width: 100%;
        height: 100%;
        background-color: red;
        position: relative;
        z-index: -1;
        @media(min-width:750px){
            width: 100%;
        }
        &_div1{
            width: 100%;
            height: 100%;
            img{
                width: 100%;
                height: 100%;
            }
        }
        &_container-inforamcao{
            position: absolute;
            width: 100%;
            height: 250px;
            background-color: black;
            top: 0;
        }
    }    
} 
</style>