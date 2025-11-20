<template>
  <section
    class="w-full bg-cover bg-center md:py-0 py-12"
    :style="{
      backgroundImage: `url(${backgroundImage})`,
      backgroundBlendMode: 'overlay',
      backgroundColor: 'linear-gradient(to bottom right, rgba(10,92,46,0.9), rgba(0,129,53,0.85))'
    }"
  >
    <div class="max-w-7xl mx-auto px-6 grid grid-cols-1 lg:grid-cols-2 gap-10">

      <!-- ESQUERDA — PASSOS -->
      <div class="flex flex-col justify-center">

        <h2 class="text-3xl md:text-4xl font-extrabold mb-8 text-white">
          Como funciona o aluguel?
        </h2>

        <!-- Botões dos passos -->
        <div class="flex flex-wrap gap-4 mb-6">
          <button
            v-for="(step, index) in steps"
            :key="index"
            @click="current = index"
            class="rounded-full flex items-center justify-center font-bold transition-all border-2
            w-10 h-10 text-md
            sm:w-12 sm:h-12 sm:text-lg"
            :class="current === index
              ? 'bg-yellow-500 text-white border-yellow-600 shadow-lg scale-110'
              : 'bg-white text-gray-700 border-gray-400 hover:bg-yellow-300 hover:text-white'
            "
          >
            {{ index + 1 }}
          </button>
        </div>

        <!-- Texto do passo -->
        <h3 class="text-lg sm:text-xl font-extrabold text-white mb-3">
          {{ steps[current].title }}
        </h3>

        <p class="text-gray-300 leading-relaxed text-base sm:text-lg">
          {{ steps[current].description }}
        </p>

        <button
          class="text-white font-semibold bg-yellow-500 hover:bg-yellow-600
          rounded-xl py-3 px-6 w-full sm:w-64 mt-6 transition-all hover:scale-[102%]"
        >
          Solicitar Cotação
        </button>

      </div>

      <!-- DIREITA — IMAGEM -->
      <div class="flex items-center justify-center">
        <img
          :src="steps[current].image"
          alt="Imagem do passo"
          class="w-3/4 sm:w-2/3 md:w-full m"
        />
      </div>

    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import Passo1 from '../../assets/images/passo1.png'
import Passo2 from '../../assets/images/passo2.png'
import Passo3 from '../../assets/images/passo3.png'
import Passo4 from '../../assets/images/passo4.png'
import Background from '../../assets/images/bg-passo-passo.png'

const steps = [
  {
    title: 'Escolha o veículo ideal',
    description: 'Selecione o modelo que melhor combina com sua necessidade: econômico, sedan, SUV ou luxo.',
    image: Passo1
  },
  {
    title: 'Escolha as datas',
    description: 'Defina a data de retirada e devolução do veículo de forma rápida e intuitiva.',
    image: Passo2
  },
  {
    title: 'Finalize sua reserva',
    description: 'Preencha suas informações e confirme a reserva com poucos cliques.',
    image: Passo3
  },
  {
    title: 'Retire e aproveite',
    description: 'Vá ao ponto de retirada, receba o veículo e curta a experiência sem complicações!',
    image: Passo4
  },
]

const current = ref(0)
const backgroundImage = Background
</script>
