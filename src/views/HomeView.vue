<script setup>
  import Hero from '../components/home/Hero.vue';
  import Frota from '../components/home/Frota.vue';
  import Beneficios from '../components/home/Beneficios.vue';
  import Marcas from '../components/home/Marca.vue';
  import LugaresViajar from '../components/home/LugaresViajar.vue';
  import PassoaPasso from '../components/home/PassoaPasso.vue'
  import Cta from '../components/home/Cta.vue';
</script>

<template>
  <main>
    <div class="pt-10 bg-[#006931]">
       <Hero/>
    </div>

    <Frota/>
    <Marcas/>
    <PassoaPasso class=" bg-green-600/80"/>
    <LugaresViajar/>
    <Cta/>
  </main>
</template>
