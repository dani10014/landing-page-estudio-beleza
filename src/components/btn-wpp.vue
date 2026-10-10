<template>
    <div class="wpp-container">
        
    </div>
</template>
<script setup lang="ts">

</script>
<style lang="scss" scoped>
@use "../component-scss/variaveis.scss";

    .menu{
        position:fixed;
        top:0;
        width:100%;
        background-color:rgba(0, 0, 0, 0.8);
        height:100vh;
        &_botoes{
            display:flex;
            flex-direction:column;
            justify-content:center;
            align-items:center;
            position:absolute;
            top:10%;
            
            width:100%;
            padding:0 variaveis.$margenSite;
            button{
                width: 50%;
                height:100px;
                background-color:transparent;
                color:white;
                border:none;
                border-bottom:1px solid white;
                @include variaveis.hoverBotao;
            }
        }
    }


</style>