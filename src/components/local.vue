<template>
    <section id="Local" class="secao-pagina">
        <h2 class="titulo">Local</h2>
        <div class="container-local">
            <div class="container-local_div1">
                <img src="../assets/IMG-20261008-WA0018.jpg">
            </div>
            <div class="container-local_div1">
                <img src="../assets/IMG-20261008-WA0011.jpg">
            </div>
            <div class="container-local_container-informacao">
                <div class="card">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="icon-atendimento">
                        <path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"></path>
                        <circle cx="12" cy="7" r="4"></circle>
                    </svg>
                    <h4>Atendimento</h4>
                    <p class="subtitulo">* Atendimento individual</p>
                    <h6>Aqui o seu momento é único. Os atendimentos são individuais e com horário agendado, garantindo total privacidade, atenção dedicada e zero filas de espera.</h6>
                </div>
                <div class="card">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="icon-local">
                        <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
                        <circle cx="12" cy="10" r="3"></circle>
                    </svg>
                    <h4>Local</h4>
                    <p class="subtitulo"> * Bonito Ms</p>
                </div>
                <div class="card">
                    <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d807.5963355722566!2d-56.491258!3d-21.129848!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x947c58d50c8407c7%3A0x4de9a9fbc7e1ac30!2sBonito%20-%20MS%2C%20Brasil!5e0!3m2!1spt-BR!2spy!4v1792274692496!5m2!1spt-BR!2spy" width="100%" height="100%" style="border:0;" allowfullscreen loading="lazy" referrerpolicy="strict-origin-when-cross-origin"></iframe>
                </div>
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
    @media(min-width:750px){
        height: 700px;
    }
    @media(max-width: 749px){
        height: auto;
        min-height: 100vh;
        padding-bottom: 2rem;
    }
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
        height: auto;
        flex: 1;
        min-height: 0;
        justify-content: center;
        position: relative;
        margin: variaveis.$espacamentoTextos-md 0;
        @media(min-width:750px){
            max-width: 1062px;
        }
        @media(max-width: 749px){
            display: block;
            flex: none;
            min-height: auto;
            padding-bottom: 1rem;
        }
        &_div1{
            width: 100%;
            height: 100%;
            img{
                width: 100%;
                height: 100%;
                object-fit: cover;
            }
            @media(max-width: 749px){
                width: 100%;
                height: 180px;
                margin-bottom: 0.75rem;
            }
        }
        &_container-informacao{
            position: absolute;
            z-index: 10;
            display: flex;
            justify-content: space-around;
            width: 100%;
            height: 200px;
            gap: 10px;
            bottom:10px;
            border-top-left-radius:10px;
            border-top-right-radius:10px ;
            @media(max-width: 749px){
                position: static;
                display: grid;
                grid-template-columns: 1fr;
                height: auto;
                gap: 0.75rem;
                width: 100%;
            }
            .card{
                width: 100%;
                height: 100%;
                display: flex;
                flex-direction: column;
                align-items: center;
                color: #f7f1ea;
                border-radius: 12px;
                margin:0 variaveis.$espacamentoTextos-sm;
                padding: 0.8rem;
                transition: all 0.3s ease-in-out;
                background: linear-gradient(135deg, rgba(118, 98, 82, 0.92), rgba(169, 141, 110, 0.88));
                border: 1px solid rgba(255, 255, 255, 0.18);
                box-shadow: 0 10px 24px rgba(0, 0, 0, 0.18);
                @media(max-width: 749px){
                    margin: 0;
                    min-height: 180px;
                    padding: 1rem;
                }
                &:hover{
                    transform: translateY(-4px) scale(1.02);
                    box-shadow: 0 16px 28px rgba(0, 0, 0, 0.22);
                    filter: brightness(1.05);
                }
                svg{
                    margin-bottom: variaveis.$espacamentoTextos-sm;
                }
                h4{
                    @include variaveis.fontesPrincipais;
                    font-size: 0.9rem;
                    letter-spacing: 0.08em;
                    text-align: center; 
                    margin-bottom: 0.5rem;
                }
                h6{
                    text-align: center;
                    @include variaveis.fonteParagrafos;
                }
                .subtitulo{
                    font-size: 0.5rem;
                    @include variaveis.fonteSubtilosImp;
                    margin-bottom: 1rem;
                    text-align: center;
                }
                iframe{
                    @media(max-width: 749px){
                        min-height: 220px;
                    }
                }
            }
        }
    }    
} 
</style>