<script setup>
    import { ref } from 'vue'


    import Page404 from './Page404.vue';
    import Schooling from '@/components/Schooling.vue';
    import Experiences from '@/components/Experiences.vue';
    import Skills from '@/components/Skills.vue';

    
  const presentationFilter = ref( 'courses' )
</script>

<template>
    <div id="about">
        <div class="presentation">
            <div class="presentation__text">
                <TitreNiveau2>Présentation</TitreNiveau2>
                <p>Je m'appelle Kévin PORTAIS, je suis actuellement en Formation de "Développeur Web et Web Mobile" avec le "Centre Européen de Formation". <br> 
                    Dans ce portfolio, vous allez découvrir mes premières réalisations, mes premiers pas dans le 
                    monde du développement web. <br>N'hésiter pas à revenir pour suivre mes projets et à me laisser vos avis. <br>
                    Bonne visite !
                </p>
                <router-link class="CTA" :to="{hash:'#contact'}">Me contacter</router-link>
            </div>
        
            <img src="@/assets/images/Photo.jpg" alt="Photo_Kévin">
        </div>
    
        <div class="about__filter">
            <button class="about__filter__button CTA" @click="presentationFilter='schooling'">Parcours</button>
            <button class="about__filter__button CTA" @click="presentationFilter='experiences'">Expériences</button>
            <button class="about__filter__button CTA" @click="presentationFilter='skills'">Compétences</button>  
        </div>
    
        <div class="about__content">
            <Schooling v-if="presentationFilter === 'schooling' "/>
        
            <Experiences v-if="presentationFilter === 'experiences' "/>
        
            <Skills v-if="presentationFilter === 'skills' "/>
        </div>
    </div>
</template>

<style scoped>
    .presentation {
        background-color: #EFFAFD;
        display: flex;
        padding: 10px 10%;
        gap : 20px;
        align-items: center;
        margin: 30px;
    }

    .presentation__text {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 15px;
    }

    .presentation__text p {
        width: 60%;
        text-align: justify;
        text-indent: 5%;
    }

    img {
        width: 50%;
        height: 50%;
        border-radius: 10%;
        box-shadow: -8px 5px 25px #EFA48B;
    }

    .about__filter {
        display: flex;
        gap: 15px;
        margin: 15px 0;
        justify-content: center;
    }

    .about__content {
        margin-bottom: 15px;
        margin-bottom: 2em;
    }

    @media screen and (max-width: 480px) {
        .presentation {
            flex-direction: column-reverse;
            padding: 10px 0;
        }
        .presentation__text p {
            width: 85%;
        }
        img {
            width: 50%;
        }
    }
</style>