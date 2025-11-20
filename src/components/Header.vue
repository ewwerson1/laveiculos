<script setup>
import { ref, onMounted, onUnmounted, computed } from "vue"
import '@fortawesome/fontawesome-free/css/all.css'

// Import das logos
import logoNormal from '../assets/icons/logo-normal.png'
import logoScrolled from '../assets/icons/logo.png'

const isScrolled = ref(false)
const isMenuOpen = ref(false) // Novo estado para o menu mobile

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

onMounted(() => {
  window.addEventListener("scroll", handleScroll)
})

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll)
})

// Troca da logo dinamicamente
const currentLogo = computed(() => {
  return isScrolled.value ? logoScrolled : logoNormal
})
</script>

<template>
  <header>
    <div
      :class="[
        'py-3 fixed z-30 w-full transition-all duration-300',
        isScrolled ? 'bg-white shadow-lg text-zinc-900' : 'bg-transparent text-zinc-50'
      ]"
    >
      <nav class="mx-auto flex items-center justify-between max-w-6xl px-4 sm:px-6 lg:px-8">

        <div class="logo z-50">
          <img :src="currentLogo" alt="Logo" class="w-20 transition-all duration-300">
        </div>

        <div class="relative hidden md:block">
          <input
            type="text"
            placeholder="Buscar veículo..."
            class="px-4 w-90 py-2 pr-10 rounded-lg bg-zinc-100 border border-zinc-300 focus:outline-none focus:ring-2 focus:ring-yellow-500 transition text-zinc-900"
          />
          <i class="fas fa-search absolute right-3 top-1/2 -translate-y-1/2 text-zinc-600"></i>
        </div>

        <div class="hidden lg:flex items-center gap-6 font-normal">
          <router-link to="/" class="hover:text-green-200 transition">Início</router-link>
          <router-link to="/frota" class="hover:text-green-200 transition">Frota</router-link>
          <router-link to="/contato" class="hover:text-green-200 transition">Como funciona</router-link>
          <router-link to="/contato" class="hover:text-green-200 transition">Newsletter</router-link>
          <router-link
            to="/contato"
            class="bg-green-200 text-green-900 transition py-2 px-4 rounded-xl font-medium hover:bg-green-300"
          >
            Seja um investidor
          </router-link>
        </div>

        <button
          @click="toggleMenu"
          class="lg:hidden z-50 p-2 rounded-lg"
          :class="isScrolled ? 'text-zinc-900' : 'text-zinc-50'"
        >
          <i v-if="isMenuOpen" class="fas fa-times text-2xl"></i>
          <i v-else class="fas fa-bars text-2xl"></i>
        </button>
      </nav>
    </div>

    <div
      :class="[
        'fixed top-0 right-0 h-full w-90 bg-white shadow-2xl transition-transform duration-500 ease-in-out z-40 lg:hidden p-6 pt-20',
        isMenuOpen ? 'translate-x-0' : 'translate-x-full'
      ]"
    >
      <div class="flex flex-col gap-4 text-zinc-900 font-medium">

        <div class="relative w-full mb-4">
          <input
            type="text"
            placeholder="Buscar veículo..."
            class="px-4 w-full py-2 pr-10 rounded-lg bg-zinc-100 border border-zinc-300 focus:outline-none focus:ring-2 focus:ring-yellow-500 transition text-zinc-900"
          />
          <i class="fas fa-search absolute right-3 top-1/2 -translate-y-1/2 text-zinc-600"></i>
        </div>

        <router-link @click="toggleMenu" to="/" class="hover:text-green-700 transition border-b border-zinc-100 py-2">Início</router-link>
        <router-link @click="toggleMenu" to="/frota" class="hover:text-green-700 transition border-b border-zinc-100 py-2">Frota</router-link>
        <router-link @click="toggleMenu" to="/contato" class="hover:text-green-700 transition border-b border-zinc-100 py-2">Como funciona</router-link>
        <router-link @click="toggleMenu" to="/contato" class="hover:text-green-700 transition border-b border-zinc-100 py-2">Newsletter</router-link>

        <router-link
          @click="toggleMenu"
          to="/contato"
          class="bg-green-900 text-white text-center transition py-3 px-4 rounded-xl mt-4 font-semibold hover:bg-green-700"
        >
          Seja um investidor
        </router-link>
      </div>
    </div>

    <div
      v-if="isMenuOpen"
      @click="toggleMenu"
      class="fixed inset-0 bg-black/50 z-30 transition-opacity duration-300 lg:hidden"
    ></div>

  </header>
</template>

<style scoped>
/* Adicione estilos específicos aqui, se necessário */
</style>
