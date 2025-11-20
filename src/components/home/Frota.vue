<template>
  <section
    class="w-full py-18 bg-cover bg-center bg-no-repeat text-zinc-800"
    :style="`background-image: url(${bgFrota});`"
  >
    <div class="max-w-7xl mx-auto px-6">

      <h2 class="text-4xl md:text-2xl font-extrabold text-center mb-10 text-gray-900">
        Nossa Frota
      </h2>

      <div class="relative">

        <!-- Botões aparecem somente no DESKTOP -->
        <button
          v-if="!isMobile"
          @click="prev"
          class="absolute left-0 top-1/2 transform -translate-y-1/2 bg-green-700 text-white p-3 rounded-full shadow-lg z-20 hover:bg-green-800 transition-all"
        >
          &#10094;
        </button>

        <button
          v-if="!isMobile"
          @click="next"
          class="absolute right-0 top-1/2 transform -translate-y-1/2 bg-green-700 text-white p-3 rounded-full shadow-lg z-20 hover:bg-green-800 transition-all"
        >
          &#10095;
        </button>

        <!-- MOBILE: scroll horizontal com dedo -->
        <div
          v-if="isMobile"
          class="flex gap-4 overflow-x-auto snap-x snap-mandatory px-2 pb-4 scrollbar-hide"
        >
          <div
            v-for="(car, index) in cars"
            :key="index"
            class="snap-start min-w-[85%] mr-4 flex-shrink-0"
          >
            <div class="bg-white rounded-2xl shadow-lg overflow-hidden">
              <img :src="car.image" :alt="car.name" class="w-full h-48 object-cover" />
              <div class="p-6 flex flex-col justify-between h-[200px]">
                <div>
                  <span class="text-sm text-green-700 font-semibold uppercase">{{ car.category }}</span>
                  <h3 class="text-xl font-bold mt-2">{{ car.name }}</h3>
                </div>
                <div class="mt-4 flex flex-col items-start justify-between">
                  <p class="text-zinc-500 text-sm">A partir de</p>
                  <span class="text-lg font-semibold text-gray-900">{{ car.price }}/dia</span>
                  <button class="mt-2 px-4 py-2 bg-green-700 text-white font-semibold rounded-lg hover:bg-green-800">
                    Alugar Agora
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- DESKTOP: carrossel tradicional -->
        <div v-else class="flex overflow-hidden">
          <div
            class="flex transition-transform duration-500"
            :style="{ transform: `translateX(-${currentIndex * (100 / visible)}%)` }"
          >
            <div
              v-for="(car, index) in cars"
              :key="index"
              class="flex-shrink-0 w-full md:w-1/3 p-4"
            >
              <div class="bg-white py-4 rounded-2xl shadow-lg overflow-hidden transition-transform hover:scale-105">
                <img :src="car.image" :alt="car.name" class="w-full md:h-48 object-cover" />
                <div class="p-6 flex flex-col justify-between h-[200px]">
                  <div>
                    <span class="text-sm text-green-700 font-semibold uppercase">{{ car.category }}</span>
                    <h3 class="text-xl font-bold mt-2">{{ car.name }}</h3>
                  </div>
                  <div class="mt-4 flex flex-col items-start justify-between">
                    <p class="text-zinc-500 text-sm">A partir de</p>
                    <span class="text-lg font-semibold text-gray-900">{{ car.price }}/dia</span>
                    <button class="mt-2 px-4 py-4 bg-green-700 text-white font-semibold rounded-lg hover:bg-green-800">
                      Alugar Agora
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Botão para ver todos os carros -->
        <div class="flex justify-center mt-10">
          <button class="px-8 py-4 border border-green-700 hover:bg-green-700 text-green-700 font-semibold rounded-lg transition-all hover:text-white cursor-pointer duration-200">
            Ver Todos os Carros ->
          </button>
        </div>

      </div>

    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue"
import bgFrota from "../../assets/images/bg-frota.png"
import Carro1 from "../../assets/images/carro1.png"
import Carro2 from "../../assets/images/carro2.png"
import Carro3 from "../../assets/images/carro3.png"
import Carro4 from "../../assets/images/carro4.png"

const cars = [
  { category: "Econômico", name: "Fiat Uno", price: "R$ 120", image: Carro1 },
  { category: "Sedan", name: "Toyota Corolla", price: "R$ 180", image: Carro3 },
  { category: "SUV", name: "Jeep Compass", price: "R$ 250", image: Carro2 },
  { category: "Luxo", name: "Mercedes-Benz C-Class", price: "R$ 450", image: Carro4 },
]

const currentIndex = ref(0)
const visible = ref(3)
const isMobile = ref(false)

const updateLayout = () => {
  isMobile.value = window.innerWidth < 768
  visible.value = isMobile.value ? 3 : 3 // desktop continua 3
}

onMounted(() => {
  updateLayout()
  window.addEventListener("resize", updateLayout)
})

onUnmounted(() => {
  window.removeEventListener("resize", updateLayout)
})

const prev = () => {
  currentIndex.value = Math.max(currentIndex.value - 1, 0)
}

const next = () => {
  currentIndex.value = Math.min(
    currentIndex.value + 1,
    cars.length - visible.value
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
