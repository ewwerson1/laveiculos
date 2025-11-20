<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="general">
    <Header/>
    <RouterView />
    <Footer/>
  </div>
</template>

<style>
.general{
    font-family: "Lato", sans-serif;
}
</style>
