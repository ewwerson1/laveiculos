<script setup>
import bgHero from '@/assets/images/bg-hero.png'
</script>

<template>
  <section
    class="relative w-full bg-[#006931] h-[500px] md:h-[650px] flex items-end bg-contain bg-center bg-no-repeat"
    :style="{ backgroundImage: `url(${bgHero})` }"
  >
    <!-- Container -->
    <div class="max-w-6xl w-full mx-auto flex justify-center md:justify-start px-16 pb-10 md:pb-30">
      <button
        class="px-8 bg-green-100 w-72 py-4 cursor-pointer text-green-900 text-lg font-semibold rounded-lg shadow-xl border  transition-all"
      >
        Reservar Agora
      </button>
    </div>
  </section>
</template>
