<template>
    <section
      class="w-full bg-gray-50 py-16 bg-cover bg-center bg-no-repeat"
      :style="`background-image: url(${bgImg});`"
    >

    <div class="max-w-3xl mx-auto px-6 text-center">

      <!-- TÍTULO -->
      <h2 class="text-gray-700 text-lg font-semibold">
        RECEBA NOVIDADES E PROMOÇÕES EM SEU E-MAIL
      </h2>

      <!-- FORM -->
      <div class="mt-8 space-y-4">
        <div class="flex flex-col md:flex-row gap-4">
          <input
            type="text"
            placeholder="Nome *"
            class="w-full bg-white border border-gray-300 px-4 py-2 rounded-md focus:outline-none"
          />

          <div class="flex gap-2 w-full">
            <select
              class="w-24 border border-gray-300 px-4 py-2 rounded-md bg-white"
            >
              <option>+55</option>
              <option>+351</option>
              <option>+1</option>
            </select>

            <input
              type="text"
              placeholder="Telefone *"
              class="w-full border bg-white border-gray-300 px-4 py-2 rounded-md focus:outline-none"
            />
          </div>
        </div>

        <input
          type="email"
          placeholder="Email *"
          class="w-full border bg-white border-gray-300 px-4 py-2 rounded-md focus:outline-none"
        />

        <!-- BOTÃO -->
        <button
          class="w-full bg-green-600 hover:bg-green-700 text-white font-semibold py-3 rounded-md transition"
        >
          CADASTRAR
        </button>

        <!-- ÍCONES -->
        <div class="flex justify-center gap-5 pt-4 text-green-600 text-xl">
          <i class="bi bi-instagram cursor-pointer"></i>
          <i class="bi bi-youtube cursor-pointer"></i>
          <i class="bi bi-facebook cursor-pointer"></i>
          <i class="bi bi-linkedin cursor-pointer"></i>
          <i class="bi bi-telegram cursor-pointer"></i>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import bgImg from '../../assets/images/bg-cta.png'
</script>

<style>

</style>
