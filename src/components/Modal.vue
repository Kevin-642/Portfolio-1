<script setup>
    const props = defineProps(['projet'])
</script>

<template>
    <div class="modal__background" @click="$emit('close')"></div>
    <div class="modal">
        <span class="material-symbols-outlined" @click="$emit('close')">close</span>
        
        <h3 class="modal__header">{{ projet.name }}</h3>

        <div class="modal__aside">
            <ul class="modal__techno">
                <p v-if="projet.tag.length == 1">Technologie :</p>
                <p v-else-if="projet.tag.length > 1">Technologies :</p>
                <p></p>
                <li v-for="i in projet.tag">{{ i }}</li>
            </ul>
            <p>Date de création : {{ projet.createDate }}</p>
        </div>

        <div class="modal__main">
            <div class="modal__images">
                <h3 v-if="projet.image.length<2">Image</h3>
                <h3 v-else>Images</h3>
                <img v-for="i in projet.image" :src="i.src" :alt="i.alt">
            </div>
            <div class="modal__info">
                <h3>Informations</h3>
                <div class="modal__info__link">
                    <h4>Lien :</h4>
                    <a :href="projet.link" target="_blank">{{ projet.link }}</a>
                </div>
                <div class="modal__info__description">
                    <h4>Description</h4>
                    <p>{{ projet.description }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .modal__info {
        width: 45%;
    }

    .modal__info__description {
        text-align: justify;
    }

    .modal__info h4 {
        margin-top: 1em;
        border-top: 1px solid #B0B347;
    }

    .modal__images img {
        width: 95%;
        height: auto;
    }

    .modal__images {
        display: flex;
        gap: 15px;
        flex-wrap: wrap;
        width: 50%;
        justify-content: center;
    }

    .modal__main {
        display: flex;
        gap: 1em;
        flex-wrap: wrap;
        margin-top: 1em;
        justify-content: center;
    }

    .modal__main h3 {
        font-size: 1.2em;
    }

    .modal__aside {
        display: flex;
        flex-wrap: wrap-reverse;
        justify-content: space-between;
        gap: 2em;
    }

    .modal__techno {
        display: flex;
        gap: 2em;
    }

    .modal__header {
        font-size: 1.5em;
        border-bottom: 2px solid #B0B347;
        margin-bottom: 10px;
    }

    .modal__background {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: auto;
        border: 1px solid black;
    }

    .modal {
        position: fixed;
        top: 2.5%;
        left: 5%;
        background-color: white;
        border: 1px solid #B0B347;
        border-radius: 25px;
        box-sizing: border-box;
        height: 95%;
        width: 90%;
        padding: 1em;
        overflow: auto;
    }

    .material-symbols-outlined {
        position: absolute;
        top: 10px;
        right: 10px;
        color: #B0B347;
        cursor: pointer;
    }

    @media screen and (max-width: 480px) {
        .modal {
            top: 0;
            left: 0;
            height: 100%;
            width: 100%;
            border-radius: 0;
        }

        .modal__main {
            flex-direction: column-reverse;
        }

        .modal__images, .modal__info{
            width: 95%;
        }
    }
</style>