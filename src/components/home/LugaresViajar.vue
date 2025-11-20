<template>
  <section class="w-full py-16 bg-white">
    <div class="max-w-7xl mx-auto px-6">

      <!-- TÍTULO -->
      <div class="text-center mb-10">
        <h2 class="text-xl font-bold text-gray-800">Destinos para descobrir e se inspirar</h2>
        <p class="text-gray-600 text-sm mt-2">
          Mais do que alugar carros, nós cuidamos do seu caminho.
        </p>
      </div>

      <!-- CARROSSEL -->
      <div class="relative">

        <!-- SETA ESQUERDA -->
        <button
          @click="prev"
          class="absolute left-0 top-1/2 -translate-y-1/2 bg-white shadow-lg w-10 h-10 rounded-full flex items-center justify-center hover:bg-green-100 transition z-10"
        >
          <i class="fa-solid fa-chevron-left text-green-700"></i>
        </button>

        <!-- LISTA DE CARDS -->
        <div
          ref="carousel"
          class="flex gap-6 overflow-x-auto no-scrollbar scroll-smooth py-4"
        >
          <div
            v-for="(item, i) in cards"
            :key="i"
            class="min-w-[260px] rounded-xl  cursor-pointer transform hover:scale-105 transition"
          >
            <!-- IMAGEM COM EFEITO ITÁLICO -->
            <div class="overflow-hidden rounded-xl">
              <img
                :src="item.image"
                class="w-full h-48 object-cover transform skew-y-[-6deg] rounded-3xl transition-all duration-300 "
              />
            </div>

            <div class="p-4">
              <h3 class="font-bold text-green-700">{{ item.title }}</h3>
              <p class="text-sm text-gray-600 uppercase">{{ item.subtitle }}</p>
            </div>
          </div>
        </div>

        <!-- SETA DIREITA -->
        <button
          @click="next"
          class="absolute right-0 top-1/2 -translate-y-1/2 bg-white shadow-lg w-10 h-10 rounded-full flex items-center justify-center hover:bg-green-100 transition z-10"
        >
          <i class="fa-solid fa-chevron-right text-green-700"></i>
        </button>

      </div>

      <!-- BOTÃO FINAL -->
      <div class="text-center mt-10">
        <button
          class="px-6 py-3 border-2 border-green-700 text-green-700 rounded-lg font-semibold hover:bg-green-700 hover:text-white transition"
        >
          Conferir todos os destinos
        </button>
      </div>

    </div>
  </section>
</template>

<script setup>
import { ref } from "vue"
import "@fortawesome/fontawesome-free/css/all.css"
import Rio from '../../assets/images/rio.webp'
import Paraiba from '../../assets/images/joao-pessoa.jpg'
const carousel = ref(null)

const cards = [
  {
    image: Rio,
    title: "O que fazer em Niterói, RJ?",
    subtitle: "Rio de Janeiro",
  },
  {
    image: Paraiba,
    title: "O que fazer em João Pessoa?",
    subtitle: "Paraíba",
  },
  {
    image: 'https://passagenspromo.com.br/blog/wp-content/uploads/2019/02/o-que-fazer-em-brasilia.jpg',
    title: "O que fazer em Brasília, DF?",
    subtitle: "Distrito Federal",
  },
  {
    image: "https://www.quintoandar.com.br/guias/wp-content/uploads/2025/02/cidades-historicas-de-minas-gerais-1.webp",
    title: "O que fazer em Ouro Preto?",
    subtitle: "Minas Gerais",
  },
]

const next = () => {
  carousel.value.scrollBy({ left: 300, behavior: "smooth" })
}

const prev = () => {
  carousel.value.scrollBy({ left: -300, behavior: "smooth" })
}
</script>

<style>
.no-scrollbar::-webkit-scrollbar {
  display: none;
}
.no-scrollbar {
  scrollbar-width: none;
}
</style>
