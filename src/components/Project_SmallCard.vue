<script setup>
    const props = defineProps( ['projet'])
</script>

<template>
    <div class="SmallCard">
        <div class="polaroid">
            <div class="polariod__image">
                <img :src="projet.image[0].src" :alt="projet.image[0].alt">
            </div>
            <p class="caption">
                <span class="material-symbols-outlined">zoom_in</span>
                {{ projet.name }}</p>
        </div>
    </div>
</template>

<style scoped>
    .SmallCard {
        width: 250px;
    }

    .SmallCard:hover .polaroid{
        background-color: rgba(90, 90, 90, 0.2);
    }

    .polaroid {
        height: 250px;
        border-radius: 20px;
        padding: 10px;
        box-shadow: -4px 5px 25px #B0B347;
        background-color: white;
        cursor: pointer;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }

    .polaroid img {
        width: 100%;
        height: auto;
        max-height: 205px;
    }

    .polariod__image {
        margin: auto;
    }

    .caption {
        padding-top: 5px;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
    }

    .material-symbols-outlined {
        color: #B0B347;
    }
</style>