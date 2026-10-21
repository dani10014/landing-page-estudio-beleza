<template>
    <section id="Contato" class="secao-pagina contato">
        <div class="contato_conteudo" data-aos="fade-up">
            <p class="contato_chamada">Vamos conversar?</p>
            <h2 class="contato_titulo">Contato</h2>
            <p class="contato_descricao">Escolha seu canal preferido para falar comigo</p>
            <div class="contato_cards">
                <a
                    class="contato_card contato_card-whatsapp"
                    href="https://wa.me/5567992417712?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio."
                    target="_blank"
                    rel="noopener noreferrer"
                    aria-label="Entre em contato pelo WhatsApp"
                >
                    <i class="fa-brands fa-whatsapp" aria-hidden="true"></i>
                    <span class="contato_card-texto">
                        <strong>WhatsApp</strong>
                        <span>Agende seu horário</span>
                    </span>
                    <i class="fa-solid fa-arrow-up-right-from-square contato_card-seta" aria-hidden="true"></i>
                </a>
                <a
                    class="contato_card contato_card-instagram"
                    href="https://www.instagram.com/lizaquinosobrancelhas/"
                    target="_blank"
                    rel="noopener noreferrer"
                    aria-label="Acesse o Instagram"
                >
                    <i class="fa-brands fa-instagram" aria-hidden="true"></i>
                    <span class="contato_card-texto">
                        <strong>Instagram</strong>
                        <span>Acompanhe nosso trabalho</span>
                    </span>
                    <i class="fa-solid fa-arrow-up-right-from-square contato_card-seta" aria-hidden="true"></i>
                </a>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "./components-scss/variaveis" as variaveis;

.contato {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 70vh;
    padding: 4rem 0;

    &_conteudo {
        width: 100%;
        max-width: 900px;
        text-align: center;
    }

    &_chamada {
        margin-bottom: 0.5rem;
        color: variaveis.$corParagrafos;
        @include variaveis.fonteSubtilosImp;
    }

    &_titulo {
        display: table;
        margin: 0 auto 1rem;
        border-bottom: 1px solid variaveis.$corParagrafos;
        color: #fff;
        @include variaveis.fonteSubtilosImp;
    }

    &_descricao {
        margin-bottom: 2rem;
        color: #f7f1ea;
        line-height: 1.6;
        @include variaveis.fonteParagrafos;
    }

    &_cards {
        display: grid;
        grid-template-columns: 1fr;
        gap: 1rem;
        text-align: left;
    }

    &_card {
        display: flex;
        align-items: center;
        gap: 1rem;
        min-height: 100px;
        padding: 1.25rem;
        border: 1px solid rgba(247, 241, 234, 0.3);
        background: rgba(70, 58, 49, 0.72);
        color: #f7f1ea;
        text-decoration: none;
        transition: transform 180ms ease, background-color 180ms ease, border-color 180ms ease;

        &:hover {
            transform: translateY(-3px);
            background: rgba(91, 75, 62, 0.92);
            border-color: rgba(247, 241, 234, 0.65);
        }

        &:focus-visible {
            outline: 3px solid #f7f1ea;
            outline-offset: 4px;
        }

        > i:first-child {
            display: grid;
            flex: 0 0 52px;
            width: 52px;
            height: 52px;
            place-items: center;
            border-radius: 50%;
            background: rgba(247, 241, 234, 0.12);
            font-size: 1.8rem;
        }
    }

    &_card-whatsapp > i:first-child {
        color: #64c98b;
    }

    &_card-instagram > i:first-child {
        color: #e7a58e;
    }

    &_card-texto {
        display: flex;
        flex: 1;
        flex-direction: column;
        gap: 0.35rem;

        strong {
            @include variaveis.fontesPrincipais;
            font-size: 1rem;
        }

        span {
            font-size: 0.9rem;
            line-height: 1.4;
        }
    }

    &_card-seta {
        color: rgba(247, 241, 234, 0.72);
    }

    @media (min-width: 750px) {
        min-height: 500px;

        &_cards {
            grid-template-columns: repeat(2, minmax(0, 1fr));
            gap: 1.5rem;
        }

        &_card {
            min-height: 120px;
            padding: 1.5rem;
        }
    }
}
</style>