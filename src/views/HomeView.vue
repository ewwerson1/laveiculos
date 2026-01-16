<script setup>
  import Hero from '../components/home/Hero.vue';
  import Busca from '../components/home/Busca.vue';
  import Frota from '../components/home/Frota.vue';
  import Beneficios from '../components/home/Beneficios.vue';
  import Depoimentos from '../components/home/Depoimentos.vue';
  import Locais from '../components/home/Locais.vue';
  import Sobre from '../components/home/Sobre.vue';
  import SejaInvestidor from '../components/home/SejaInvestidor.vue';
  import PassoaPasso from '../components/home/PassoaPasso.vue'

</script>

<template>
  <main>
    <div class="">
       <Hero/>
    </div>
    <Busca/>
    <Frota/>

    <PassoaPasso />

  </main>
</template>
