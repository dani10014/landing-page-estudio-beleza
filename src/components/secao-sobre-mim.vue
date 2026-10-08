<template>
    <div class="container-sobre">
        <div class="container-sobre_foto-profissional" data-aos="fade-up">
            <img src="../assets/IMG-20261008-WA0006.jpg">
        </div>
        <div class="container-sobre_nome">
            <h2>Liz Aquino</h2>
            <p>Designer de sobrancelha</p>
        </div>
    </div>
</template>
<script setup lang="ts">

</script>
<style lang="scss" scoped>
@use "../component-scss/variaveis.scss";

    .container-sobre{
        display: flex;
        flex-direction: column;
        height: 100vh;
        width:100%;
        background: #f7f8f5;
        color: #252b27;
        &_foto-profissional{
            display: flex;
            justify-content: center;
            width: 100%;
            margin-top: 2rem;
            img{
                width:300px;
                height: 300px;
                border-radius: 50%;
            }
        }
        &_nome{
            text-align: center;
            margin: variaveis.$margenSite;
            h2{
                color:#252b27;
            }
        }
    }

</style>