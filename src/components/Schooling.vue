<script setup>
    import Page404 from './Page404.vue';

    const parcours = {
        annee1: {
            ecole: 'CFA Pommerit-Jaudy(22) - LTP Nay-Baudreix(64)',
            date: 'Septembre 2003 - Juin 2005',
            title: 'BEP Agricole',
            comment: 'Conduite et Gestion d une exploitation agricole - Élevage du cheval'
        },
        annee2: {
            ecole: 'École des Gendarmes Adjoints Volontaires de Tulle (19)',
            date: 'Février 2006 - Mai 2006',
            title: 'Gendarme Adjoint Volantaire',
            comment: 'Agent de Police Judiciaire Adjoint'
        },
        annee3: {
            ecole: 'ERP Jean JANVIER de Rennes (35)',
            date: 'Octobre 2010 - Décembre 2010',
            title: 'CQP APS/SSIAP1',
            comment: 'Agent de Prévention et de Sécurité / Agent de Service de Sécurité Incendie et d Assistance à Personnes'
        },
        annee4: {
            ecole: 'ASFO de Pau (64)',
            date: 'Janvier 2012 - Mars 2012',
            title: 'CQP ACS',
            comment: 'Agent Cynophile de Sécurité'
        },
        annee5: {
            ecole: 'Centre Européen de Formation',
            date : 'Avril 2024 - En cours',
            title: 'Titre Professionnel niveau 5 - Développeur web et Web mobile',
            comment: 'Technologies : HTML - CSS - JavaScript - Vue.Js - Git/GitHub '
        }
    }
</script>

<template>
    <div class="courses">
        <div class="courses__title">
            <span class="material-symbols-outlined">history_edu</span><br>
            <TitreNiveau2>Mon parcours</TitreNiveau2>
        </div>
    
        <div class="parcours">
            <div class="ecole" v-for="annee in parcours">
                <h3 class="ecole__title">{{ annee.ecole }}</h3>
                <h4 class="ecole__info">{{ annee.title }} <span class="separation">|</span> {{ annee.date }}</h4>
                <p class="ecole__comment">{{ annee.comment }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .courses {
        width: 60%;
        display: flex;
        flex-direction: column;
        align-items: center;
        margin: auto;
    }

    .courses__title {
        text-align: center;
    }

    .material-symbols-outlined {
        font-size: 4em;
    }

    .ecole__title {
        font-size: 1.25em;
    }

    .ecole__info {
        font-size: 1.05em;
    }

    .separation {
        font-style: italic;
        color: #EFA48B;
    }

    .ecole__comment {
        text-indent: 2em;
        text-align: justify;
    }

    .parcours {
        margin-top: 15px;
        display: flex;
        flex-direction: column-reverse;
        gap: 25px;
    }

    .ecole {
        padding: 15px;
        background-color: #EFFAFD;
        border-radius: 25px;
        box-shadow: -4px 5px 10px #B0B347;
    }

    @media screen and (max-width: 480px) {
        .courses {
            width: 85%;
        }
    }
</style>