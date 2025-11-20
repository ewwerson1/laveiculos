<template>
  <section class="w-full py-16 bg-white text-text-700">
    <div class="max-w-7xl mx-auto px-6">

      <h2 class="text-4xl md:text-2xl font-extrabold text-center mb-10">
        Encontre seu carro pela marca
      </h2>

      <div class="relative bg-yellow-400/90 rounded-2xl py-6">

        <!-- Botões só aparecem no DESKTOP -->
        <button
          v-if="!isMobile"
          @click="prev"
          class="absolute -left-4 top-1/2 transform -translate-y-1/2 bg-yellow-600 text-white p-3 rounded-full shadow-lg z-20 hover:bg-yellow-700 transition-all"
        >
          &#10094;
        </button>

        <button
          v-if="!isMobile"
          @click="next"
          class="absolute -right-4 top-1/2 transform -translate-y-1/2 bg-yellow-600 text-white p-3 rounded-full shadow-lg z-20 hover:bg-yellow-700 transition-all"
        >
          &#10095;
        </button>

        <!-- MOBILE: deslizar com o dedo -->
        <div
          v-if="isMobile"
          class="flex gap-4 overflow-x-auto snap-x snap-mandatory scrollbar-hide px-4 pb-4"
        >
          <div
            v-for="(brand, index) in brands"
            :key="index"
            class="snap-start min-w-[45%] bg-yellow-300/40 rounded-xl py-8 flex flex-col items-center justify-center hover:scale-105 transition-transform cursor-pointer"
          >
            <img :src="brand.image" :alt="brand.name" class="h-20 object-contain" />
            <h1 class="font-semibold mt-3">{{ brand.name }}</h1>
          </div>
        </div>

        <!-- DESKTOP/TABLET: carrossel tradicional -->
        <div v-else class="overflow-hidden">
          <div
            class="flex transition-transform duration-500"
            :style="{ transform: `translateX(-${currentIndex * (100 / visible)}%)` }"
          >
            <div
              v-for="(brand, index) in brands"
              :key="index"
              class="flex-shrink-0 w-[25%] md:w-[33%] lg:w-[25%] flex justify-center"
            >
              <div class="p-12 flex flex-col items-center justify-center hover:scale-105 cursor-pointer transition-transform">
                <img :src="brand.image" :alt="brand.name" class="h-24 object-contain" />
                <h1 class="font-semibold mt-3">{{ brand.name }}</h1>
              </div>
            </div>
          </div>
        </div>

      </div>

      <!-- Botão ver todas as marcas -->
      <div class="flex justify-center mt-10">
        <button class="px-6 py-3 bg-green-800 hover:bg-green-900 text-white font-semibold rounded-lg transition-all">
          Ver Todas os Carros ->
        </button>
      </div>

    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue"

import Toyota from '@/assets/images/toyota.svg'
import Renault from '@/assets/images/renault.png'
import Nissan from '@/assets/images/nissan.png'
import Jeep from '@/assets/images/jeep.svg'
import Honda from '@/assets/images/honda.png'
import Fiat from '@/assets/images/fiat.svg'
import Chevrolet from '@/assets/images/chevrolet.png'
import Volkswagen from '@/assets/images/volkswagen.png'
import Byd from '@/assets/images/byd.svg'

const brands = [
  { name: 'Toyota', image: Toyota },
  { name: 'Renault', image: Renault },
  { name: 'Nissan', image: Nissan },
  { name: 'Jeep', image: Jeep },
  { name: 'Honda', image: Honda },
  { name: 'Fiat', image: Fiat },
  { name: 'Chevrolet', image: Chevrolet },
  { name: 'Volkswagen', image: Volkswagen },
  { name: 'Byd', image: Byd },
]

const currentIndex = ref(0)
const visible = ref(4)
const isMobile = ref(false)

const updateVisible = () => {
  if (window.innerWidth < 768) {
    isMobile.value = true
    visible.value = 2
  } else if (window.innerWidth < 1024) {
    isMobile.value = false
    visible.value = 3
  } else {
    isMobile.value = false
    visible.value = 4
  }
}

onMounted(() => {
  updateVisible()
  window.addEventListener("resize", updateVisible)
})

onUnmounted(() => {
  window.removeEventListener("resize", updateVisible)
})

const prev = () => {
  currentIndex.value = Math.max(currentIndex.value - 1, 0)
}

const next = () => {
  currentIndex.value = Math.min(
    currentIndex.value + 1,
    brands.length - visible.value
  )
}
</script>

<style>
/* Esconde scrollbar no mobile */
.scrollbar-hide::-webkit-scrollbar {
  display: none;
}
.scrollbar-hide {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>
