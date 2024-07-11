<script setup>
  import ContactForm from '@/components/ContactForm.vue';
  import Presentation from '@/components/Presentation.vue';
  import Projects from '@/components/Projects.vue';
  

  let aboutLink = document.getElementById("about__link")
  let projectLink = document.getElementById("project__link")
  let contactLink = document.getElementById("contact__link")

  function activeLink(e){
    e.style.color='#8957ee'
    e.style.textDecoration="underline"
    e.style.fontWeight=700
  }

  function removeLink(e){
    e.style.textDecoration="none"
    e.style.fontWeight=400
    e.style.color="#B0B347"
  }
</script>

<template>
    <Presentation @pointerenter="activeLink(aboutLink)" @pointerleave="removeLink(aboutLink)"/>

    <Projects @pointerenter="activeLink(projectLink)" @pointerleave="removeLink(projectLink)"/>

    <ContactForm @pointerenter="activeLink(contactLink)" @pointerleave="removeLink(contactLink)"/>
</template>

<style scoped>

</style>