<script setup>
  import Header from './components/Header.vue';
  import Footer from './components/Footer.vue';
</script>

<template>
  <Header/>

  <main>  
    <RouterView></RouterView>
  </main>

  <Footer/>
</template>

<style scoped>
</style>
