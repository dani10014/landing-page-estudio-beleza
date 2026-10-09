<template>
    <section class="servicos" id="servicos" aria-labelledby="servicos-titulo">
        <div class="servicos_conteudo">
            <div class="servicos_texto">
                <h2 id="servicos-titulo" data-aos="fade-up">Serviços</h2>

                <ul class="servicos_lista">
                    <li v-for="servico in servicos" :key="servico.nome" data-aos="fade-up" class="servicos_item">
                        <div>
                            <h3>{{ servico.nome }}</h3>
                            <p>{{ servico.descricao }}</p>
                        </div>
                    </li>
                </ul>
            </div>

            <div class="servicos_galeria" aria-label="Trabalhos de design de sobrancelhas">
                <img
                    class="servicos_foto servicos_foto-principal"
                    src="../assets/IMG-20261008-WA0003.jpg"
                    alt="Resultado de design de sobrancelhas"
                    loading="lazy"
                >
                <img
                    class="servicos_foto servicos_foto-secundaria"
                    src="../assets/IMG-20261008-WA0005.jpg"
                    alt="Detalhe de um atendimento de sobrancelhas"
                    loading="lazy"
                >
                <img
                    class="servicos_foto servicos_foto-terciaria"
                    src="../assets/IMG-20261008-WA0006.jpg"
                    alt="Resultado de cuidado de sobrancelhas"
                    loading="lazy"
                >
            </div>
            <div class="btn-agendar" data-aos="fade-up">
                <button>Agendar</button>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
const servicos = [
    {
        nome: "Design de sobrancelhas",
        descricao: "Mapeamento e cuidado para valorizar o formato natural do seu rosto.",
    },
    {
        nome: "Design com henna",
        descricao: "Mais definição para o desenho das sobrancelhas.",
    },
    {
        nome: "Brow lamination",
        descricao: "Fios alinhados para um visual mais preenchido e definido.",
    },
];
</script>

<style lang="scss" scoped>
@use "../component-scss/variaveis.scss";

.servicos {
    padding: 6rem variaveis.$margenSite;
    background: #f8f6f2;
    color: #fff;
    background: #020208;
    background: linear-gradient(140deg, rgba(2, 2, 8, 1) 24%, rgba(184, 55, 0, 1) 91%);
    &_conteudo {
        display: grid;
        grid-template-columns: minmax(0, 1fr);
        gap: 3rem;
        max-width: 1160px;
        margin: 0 auto;
        .btn-agendar{
            margin-top:2rem;
            display: flex;
            justify-content: center;
            width:100%;
            button{
                @include variaveis.estiloBotao;
                @include variaveis.fonteBotoes;
            }
        }
    }

    &_texto {
        max-width: 600px;
    }

    h2 {
        font-family: "Playfair Display", serif;
        font-size: clamp(2.5rem, 8vw, 4rem);
        font-weight: 600;
        line-height: 1.1;
    }

    &_lista {
        margin: 0;
        padding: 0;
        list-style: none;
    }

    &_item {
        display: grid;
        grid-template-columns: minmax(0, 1fr);
        gap: 0.75rem;
        align-items: start;
        padding: 1.2rem 0;
        border-top: 1px solid #d9ded8;

        h3 {
            margin-bottom: 0.4rem;
            font-family: "Montserrat", sans-serif;
            font-size: 1rem;
            font-weight: 700;
        }

        p {
            color: #fff;
            font-family: "Montserrat", sans-serif;
            font-size: 0.9rem;
            line-height: 1.6;
        }
    }

    &_galeria {
        position: relative;
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: 1fr 1fr;
        gap: 0.75rem;
        min-height: 390px;
    }

    &_foto {
        width: 100%;
        height: 100%;
        border-radius:10px;
        min-height: 0;
        object-fit: cover;
        border:1px solid #fff;
        box-shadow: 0px 0px 10px black;

        &-principal {
            grid-row: 1 / 3;
        }
    }

    @media (min-width: 800px) {
        padding: 7rem 2rem;

        &_conteudo {
            grid-template-columns: minmax(0, 0.95fr) minmax(0, 1.05fr);
            gap: 5rem;
            align-items: center;
        }

        &_item {
            grid-template-columns: minmax(0, 1fr);
            gap: 1rem;
            align-items: center;

            h3 {
                font-size: 1.05rem;
            }
        }

        &_galeria {
            min-height: 560px;
            gap: 1rem;
        }
    }
}
</style>