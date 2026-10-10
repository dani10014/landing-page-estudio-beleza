<template>
    <header>
        <div class="cabecalho" data-aos="fade-up">
            <img src="../assets/IMG-20261008-WA0004.png"  class="logo" alt="Logo - L.A - Liz Aquino">
            <button class="btn-menu" @click="ativarMenu">
                <i class="fa-solid fa-bars"></i>
            </button>
        </div>
    </header>
</template>
<script setup lang="ts">
    
    const menuFoiAtivo = defineEmits(["menuAtivo"])

    const ativarMenu =()=>{
        menuFoiAtivo("menuAtivo")
    }

</script>
<style lang="scss" scoped>
@use "../component-scss/variaveis.scss";

    header{
        position:fixed;
        top:0;
        z-index:100;
        width:100%;
        color:white;
        .cabecalho{
            display: flex;
            justify-content:space-between;
            padding:20px 30px;
            align-items:center;
            @media(min-width:750px){
                padding:30px 40px;
            }
            .logo{
                width: 40px;
                height: 50px;
                object-fit:fill;
            }
            button{
                background-color:transparent;
                color:white;
                border:none;
                font-size:1.5rem;
                cursor:pointer;
                transition:all 0.3s ease-in-out;
                &:hover{
                    color:rgba(0, 0, 0, 0.486);
                }
            }
        }
    }
</style>