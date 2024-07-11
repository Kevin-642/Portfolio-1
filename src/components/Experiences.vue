<script setup>
    import Page404 from './Page404.vue';

    const parcours = {
        annee1: {
            entreprise: 'Pyrenet - Ibos (65)',
            date: 'Mars 2022 - Mars 2024',
            title: 'Préparateur de Commandes',
        },
        annee2: {
            entreprise: 'Falliero - Ibos (65)',
            date: 'Septembre 2021 - Mars 2022',
            title: 'Magasinier - Responsable des stocks',
        },
        annee3: {
            entreprise: 'Leroy Merlin - Pau (64)',
            date: 'Mars 2014 - Septembre 2021',
            title: 'Logisticien Polyvalent',
        },
        annee4: {
            entreprise: 'Divers Société - Pau (64)',
            date: 'Décembre 2010 - Janvier 2014',
            title: 'Agent de Sécurité APS/ACS/SSIAP1',
        },
        annee4: {
            entreprise: 'Gendarmerie Nationale',
            date: 'Février 2006 - Décembre 2010',
            title: 'Gendarme Adjoint Volontaire',
        },
    }
</script>

<template>
    <div class="experience">
        <div class="experience__title">
            <span class="material-symbols-outlined">work</span><br>
            <TitreNiveau2>Mes expériences professionnelles</TitreNiveau2>
        </div>
    
        <div class="annee">
            <div class="job" v-for="annee in parcours">
                <h3 class="job__title">{{ annee.entreprise }}</h3>
                <h4 class="job__info">{{ annee.title }} <span class="separation">|</span> {{ annee.date }}</h4>
                <p class="job__comment">{{ annee.comment }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .experience {
        width: 60%;
        display: flex;
        flex-direction: column;
        align-items: center;
        margin: auto;
    }

    .experience__title {
        text-align: center;
    }

    .material-symbols-outlined {
        font-size: 4em;
    }

    .job__title {
        font-size: 1.25em;
    }

    .job__info {
        font-size: 1.05em;
    }

    .separation {
        font-style: italic;
        color: #EFA48B;
    }

    .job__comment {
        text-indent: 2em;
        text-align: justify;
    }

    .annee {
        margin-top: 15px;
        display: flex;
        flex-direction: column-reverse;
        gap: 25px;
    }

    .job {
        padding: 15px;
        background-color: #EFFAFD;
        border-radius: 25px;
        box-shadow: -4px 5px 10px grey;
    }

    @media screen and (max-width: 480px) {
        .experience {
            width: 85%;
        }
    }
</style>