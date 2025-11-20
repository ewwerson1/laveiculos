<template>
  <section class="w-full py-16 text-white bg-gradient-to-r from-green-800 via-green-900 to-green-700">
    <div class="max-w-6xl mx-auto px-6">

      <h2 class="text-4xl md:text-5xl font-extrabold text-center mb-16 text-transparent bg-clip-text bg-gradient-to-r from-white to-gray-300">
        Por que alugar conosco?
      </h2>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-5 gap-6">

        <!-- Card 1 -->
        <div class="modern-card">
          <div class="icon-circle">
            <i class="fas fa-road text-3xl text-gray-100"></i>
          </div>
          <h3 class="font-bold text-xl mb-1 text-gray-100">Quilometragem Livre</h3>
          <p class="text-sm text-gray-300">Sem limites de distância para explorar.</p>
        </div>

        <!-- Card 2 -->
        <div class="modern-card">
          <div class="icon-circle">
            <i class="fas fa-file-signature text-3xl text-gray-100"></i>
          </div>
          <h3 class="font-bold text-xl mb-1 text-gray-100">Sem Burocracia</h3>
          <p class="text-sm text-gray-300">Processo de locação ágil e digital.</p>
        </div>

        <!-- Card 3 -->
        <div class="modern-card">
          <div class="icon-circle">
            <i class="fas fa-car-side text-3xl text-gray-100"></i>
          </div>
          <h3 class="font-bold text-xl mb-1 text-gray-100">Veículos Novos</h3>
          <p class="text-sm text-gray-300">Frota revisada e atualizada.</p>
        </div>

        <!-- Card 4 -->
        <div class="modern-card">
          <div class="icon-circle">
            <i class="far fa-clock text-3xl text-gray-100"></i>
          </div>
          <h3 class="font-bold text-xl mb-1 text-gray-100">Suporte 24h</h3>
          <p class="text-sm text-gray-300">Assistência completa a qualquer hora.</p>
        </div>

        <!-- Card 5 -->
        <div class="modern-card">
          <div class="icon-circle">
            <i class="fas fa-credit-card text-3xl text-white"></i>
          </div>
          <h3 class="font-bold text-xl mb-1 text-gray-100">Pagamento Facilitado</h3>
          <p class="text-sm text-gray-300">Opções flexíveis para você.</p>
        </div>

      </div>

    </div>
  </section>
</template>

<script setup>
import '@fortawesome/fontawesome-free/css/all.css';
</script>

<style scoped>
.modern-card {
  @apply bg-gray-900/40
         p-8
         rounded-2xl
         shadow-2xl
         border-t-2
         border-l-2
         border-green-600/30
         backdrop-blur-sm
         flex
         flex-col
         items-center
         text-center
         transition-all
         duration-500
         hover:bg-gray-800/60
         hover:scale-[1.02]
         hover:shadow-green-700/20;
}

.icon-circle {
  @apply w-16
         h-16
         bg-white
         rounded-full
         flex
         items-center
         justify-center
         mx-auto
         mb-6
         shadow-inner
         shadow-green-900/50
         border-2
         border-green-700/50;
}
</style>
