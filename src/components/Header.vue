<script setup>
    import { ref } from 'vue'

    let showMenu = ref( false )
</script>

<template>
    <header>
        <nav>
            <router-link class="link__img" to="/">
                <img src="@/assets/images/main-logo.jpeg" alt="Logo">
            </router-link>
            
            <div class="sideNav__background" v-if="showMenu" @click="showMenu=false"></div>

            <div class="sideNav" v-if="showMenu">
                <span class="material-symbols-outlined link" @click="showMenu=false">close</span>
                <ul class="sideNav__list">
                    <router-link to="/#about" @click="showMenu=false">Présentation</router-link>
                    <router-link to="/#projets" @click="showMenu=false">Projets</router-link>
                    <router-link to="/#contact" @click="showMenu=false">Contact</router-link>
                </ul>
            </div>

            <span class="material-symbols-outlined burger-icon link" @click="showMenu=true">menu</span>

            <div class="nav__link">
                <router-link id="about__link" to="/#about">Présentation</router-link>
                <span>|</span>
                <router-link id="project__link" to="/#projets">Projets</router-link>
                <span>|</span>
                <router-link id="contact__link" to="/#contact">Contact</router-link>
            </div>
        </nav>
    </header>
</template>

<style scoped>
    header {
        position: fixed;
        background-color: white;
        width: 99%;
        top: 0;
        padding: 15px;
        border-bottom: 1px solid #B0B347;
        left: 5px;
        right: 5px;
    }

    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .link__img{
        padding: 5px;
    }

    img {
        width: 75px;
    }

    .nav__link * {
        font-size: 1.1em;
        padding: 5px;
        text-decoration: none;
    }

    .nav__link a {
        padding: 15px;
    }

    a:hover {
        background-color: #EFFAFD;
        border-radius: 10px;
        text-decoration: underline;
    }

    .burger-icon {
        display: none;
    }

    .sideNav {
        width: 65%;
        height: 100%;
        box-sizing: border-box;
        position: fixed;
        top: 85px;
        right: 0;
        background-color: white;
        padding: 10px;
        border: 1px solid #B0B347;
        border-top: none;
        border-right: none;
    }

    .sideNav__background {
        position: fixed;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
    }
    
    .sideNav__list {
        display: flex;
        flex-direction: column;
        gap: 15px;
        font-size: 1.1em;
        padding-right: 1em;
    }

    .link {
        cursor: pointer;
    }

    @media screen and (max-width: 480px) {
        .burger-icon {
            display: block;
            color: #B0B347;
            margin-right: 10%;
        }

        .nav__link {
            display: none;
        }
    }
</style>