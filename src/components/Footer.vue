<script setup>
    import { computed } from 'vue'

    const copyright = computed(() =>{
        const currentYear = new Date().getFullYear()
        return `© Copyright ${currentYear} | Kévin PORTAIS`
    });
</script>

<template>
    <footer class="footer">
        <div class="footer__content">
            <div class="footer__adress">
                <h3>Mes contacts</h3>
                <address>
                    <a href="mailto:kevin.portais@gmail.com">kevin.portais@gmail.com</a>
                    <a href="tel:+0626513027">06.26.51.30.27</a>
                </address>
            </div>
            <div class="footer__borderRight"></div>
            <div class="footer__social">
                <h3>Me retrouver</h3>
                <a class="footer__social__icon" href="https://x.com" target="_blank" rel="noopener noreferrer">
                    <img src="@/assets/images/twitter.png" alt="Logo X">
                </a>
                <a class="footer__social__icon" href="https://github.com/Kevin-642" target="_blank" rel="noopener noreferrer">
                    <img src="@/assets/images/gitHub.png" alt="Logo GitHub">
                </a>
                <a class="footer__social__icon" href="https://www.linkedin.com/in/kevin-p-817aa5301/" target="_blank" rel="noopener noreferrer">
                    <img src="@/assets/images/Linkedin.jpg" alt="Logo LinkedIn">
                </a>               
            </div>
        </div>
        <div class="footer__copyright">
            <p>Dernières modifications le<time datetime="2024-07-12">12 Juillet 2024</time></p>
            <p class="copyright">{{ copyright }}</p>
        </div>
    </footer>
</template>

<style scoped>
    .footer__content {
        display: flex;
        justify-content: space-evenly;
        margin-left: -87px;
        margin-right: -87px;

    }

    footer * {
        background-color: #B0B347;
        color: whitesmoke;
        padding: 10px;
        
    }
    
    .footer__borderRight {
        border-right: 1px solid grey;
    }

    address {
        display: flex;
        flex-direction: column;
    }

    .footer__copyright {
        text-align: center;
        margin-left: -87px;
        margin-right: -87px;
    }

    time {
        font-style: italic;
    }

    .copyright {
        font-style: italic;
        font-size: 0.8em;
    }

    .footer__social__icon:hover {
        opacity: 50%;
    }
</style>