<template>
    <section id="Sobre" class="secao-pagina sobre">
        <div class="sobre_conteudo" data-aos="fade-up">
            <div class="sobre_imagem">
                <img src="../assets/IMG-20261008-WA0017.jpg" alt="Espaço de beleza da Liz Aquino">
            </div>
            <div class="sobre_texto">
                <p class="sobre_chamada">Prazer, sou a Liz</p>
                <h2 class="sobre_titulo">Sobre</h2>
                <p class="sobre_descricao">
                    Sou Liz Aquino e encontrei no design de sobrancelhas e na maquiagem formas de realçar
                    a beleza que já existe em cada pessoa. Acredito em um trabalho minucioso, feito com
                    cuidado para criar resultados naturais e que respeitem a sua individualidade.
                </p>
                <p class="sobre_descricao">
                    Meu espaço nasceu do sonho de oferecer um atendimento sem pressa, longe da correria
                    dos grandes salões. Preparei um ambiente intimista, seguro e acolhedor na minha própria
                    casa, para receber cada cliente com privacidade e atenção de verdade.
                </p>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "./components-scss/variaveis" as variaveis;

.sobre {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    padding: 3rem 0;
    margin-block: 2rem;

    &_conteudo {
        display: grid;
        grid-template-columns: 1fr;
        gap: 2rem;
        width: 100%;
        max-width: 1062px;
        align-items: center;
    }

    &_imagem {
        min-height: 260px;
        overflow: hidden;
        background: rgba(214, 204, 194, 0.12);
        border: 1px solid rgba(214, 204, 194, 0.35);

        img {
            display: block;
            width: 100%;
            height: 100%;
            min-height: 260px;
            object-fit: cover;
            border-radius: 10px;
        }
    }

    &_texto {
        color: #f7f1ea;
    }

    &_chamada {
        margin-bottom: 0.75rem;
        color: variaveis.$corParagrafos;
        @include variaveis.fonteSubtilosImp;
    }

    &_titulo {
        display: table;
        margin-bottom: 1.25rem;
        border-bottom: 1px solid variaveis.$corParagrafos;
        color: #fff;
        @include variaveis.fonteSubtilosImp;
    }

    &_descricao {
        max-width: 52ch;
        margin-bottom: 1rem;
        line-height: 1.7;
        @include variaveis.fonteParagrafos;
    }

    @media (min-width: 750px) {
        min-height: 600px;

        &_conteudo {
            grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
            gap: 3rem;
        }

        &_imagem,
        &_imagem img {
            min-height: 420px;
        }
    }
}
</style>