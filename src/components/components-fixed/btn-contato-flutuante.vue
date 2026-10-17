<template>
    <div class="container-btn" data-aos="fade-up">
        <a
            class="container-btn_botao"
            href="https://wa.me/5567992417712?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio."
            target="_blank"
            rel="noopener noreferrer"
            aria-label="Agendar horário pelo WhatsApp"
        >
            <span class="container-btn_icone">
                <img src="../../assets/WhatsApp_Logo_PNG_Sem_Fundo_Transparente.png" alt="">
            </span>
            <span class="container-btn_texto">Agendar</span>
        </a>
    </div>
</template>
<style lang="scss" scoped>
    .container-btn{
        position: fixed;
        right: max(16px, env(safe-area-inset-right));
        bottom: max(18px, env(safe-area-inset-bottom));
        z-index: 20;
        &_botao{
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            min-height: 56px;
            padding: 7px 18px 7px 8px;
            border-radius: 999px;
            border: 1px solid rgba(255, 255, 255, 0.55);
            background: #128c50;
            color: #fff;
            box-shadow: 0 5px 18px rgba(0, 0, 0, 0.3);
            text-decoration: none;
            transition: transform 160ms ease, background-color 160ms ease, box-shadow 160ms ease;

            &:hover{
                background: #0c7542;
                box-shadow: 0 7px 22px rgba(0, 0, 0, 0.36);
                transform: translateY(-2px);
            }

            &:focus-visible{
                outline: 3px solid #fff;
                outline-offset: 3px;
            }

            &:active{
                transform: translateY(0) scale(0.97);
            }

            @media(min-width:750px){
                width: 56px;
                height: 56px;
                padding: 7px;
            }
        }
        &_icone{
            display: grid;
            flex: 0 0 40px;
            width: 40px;
            height: 40px;
            place-items: center;
            border-radius: 50%;
            background: #fff;
        }
        img{
            width: 31px;
            height: 31px;
            object-fit: contain;
        }
        &_texto{
            font-family: "Raleway", sans-serif;
            font-size: 0.9rem;
            font-weight: 700;
            white-space: nowrap;
        }
        @media(min-width:750px){
            right: 28px;
            bottom: 28px;
            &_texto{
                display: none;
            }
        }
    }
</style>