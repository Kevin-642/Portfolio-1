<script setup>
    import Page404 from '@/components/Page404.vue';
</script>

<template>
    <div>
        <RouterLink class="error404" to="/">
            <Page404 class="title">404</Page404>
            <p class="CTA">Revenir sur le site</p>
        </RouterLink>
    </div>
</template>

<style scoped>
    div{
        margin: 15px;
    }

    .error404 {
        background-image: url(@/assets/images/404.jpg);
        background-origin: content-box;
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        width: 50%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-evenly;
        gap: 2em;
        padding: 15vh 0;
        margin: auto;
        text-decoration: none;
       
        box-shadow: -10px 10px 25px red;
    }

    .title {
        font-size: 2em;
    }

    @media screen and (max-width: 480px) {
        .error404 {
            width: 100%;
            padding: 5vh 0;
            margin-top: 25%;
        }
    }
</style>