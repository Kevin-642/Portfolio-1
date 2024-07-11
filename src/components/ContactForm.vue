<script setup>
    import Page404 from '@/components/Page404.vue'
    import { ref, reactive } from 'vue'

    const AfficheMessageErreur = ref(false)

    const message = ref({
        name: '',
        mail: '',
        tel: '',
        object: '',
        msg: '',
    })

    function sendMail(message) {
        if (message.name.length < 1 
        || message.mail.length < 1
        || message.object.length < 1 
        || message.msg.length < 1 ){
            AfficheMessageErreur.value = true
        }else {
            AfficheMessageErreur.value = false
            let mailto
            if(message.tel) {
                mailto = `mailto:kevin.portais@gmail.com?subject=${message.object}&body=Je%20suis%20%3A%20${message.name}%0AVoici%20mon%20mail%20%3A%20${message.mail}%0AVoici%20mon%20téléphone%20%3A%20${message.tel}%0A%0A${message.msg}`
            }else {
                mailto = `mailto:kevin.portais@gmail.com?subject=${message.object}&body=Je%20suis%20%3A%20${message.name}%0AVoici%20mon%20mail%20%3A%20${message.mail}%0A%0A${message.msg}`
            }
            location.href = mailto
        }
    }
</script>

<template>
    <div id="contact">
        <TitreNiveau2 class="contact__title">Contact</TitreNiveau2>

        <div class="messageErreur" v-if="AfficheMessageErreur">
            <span class="material-symbols-outlined">Erreur</span>
            <p>Tous les champs doivent être renseignés</p>
        </div>
    
        <div class="form__grid">
            <input v-model="message.name" type="text" name="name"  id="name" placeholder="Nom...">
            <input v-model="message.mail" type="email" name="mail" id="mail" placeholder="Email...">
            <input v-model="message.tel" type="tel" name="tel" id="tel" placeholder="Téléphone...">
            <input v-model="message.object" type="text" name="object" id="object" placeholder="Objet...">
            <textarea v-model="message.msg" name="message" id="message" placeholder="Message..."></textarea>
            <button class="CTA" @click="sendMail(message)">Envoyer</button>
        </div>
    </div>
</template>

<style scoped>
    #contact {
        padding-top: 15px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .contact__title {
        margin-bottom: 25px;
    }

    .form__grid {
        margin : 10px 0px;
        width: 80%;
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        grid-gap: 10px;
    }

    input {
        height: 25px;
    }

    input:focus, textarea:focus {
        box-shadow: -4px 4px 10px #B0B347;
    }

    #name {
        grid-column: 1 / 2;
    }

    #mail {
        grid-row: 2 / 3;
    }

    #tel {
        grid-row: 3/4;
    }

    .CTA {
        width: 50%;
        margin: auto;
        grid-column: 1/3;
        grid-row: 4 / 5;
    }

    #message {
        grid-row: 2 / 4;
    }

    .messageErreur {
        display: flex;
        align-items: center;
        background-color: rgba(255, 0, 0, 0.35);
        border: 1px solid red;
        border-radius: 15px;
        padding: 5px;
    }

    .messageErreur * {
        color: red;
        font-size: 0.9em;
    }

    @media screen and (max-width: 480px) {
        .form__grid {
            display: flex;
            flex-direction: column;
        }

        #message {
            height: 6em;
        }
    }
</style>