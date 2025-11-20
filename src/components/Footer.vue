<template>
  <footer class="w-full bg-gray-100 py-12 text-gray-700 border-t">
    <div class="max-w-7xl mx-auto px-6 grid grid-cols-1 md:grid-cols-4 gap-10">

      <!-- 1 — COLUNA: Alugar um carro -->
      <div>
        <h3 class="font-bold mb-4">Alugar um carro</h3>
        <ul class="space-y-2">
          <li class="hover:underline cursor-pointer">A loja mais próxima de você</li>
          <li class="hover:underline cursor-pointer">Grupos de Carros</li>
          <li class="hover:underline cursor-pointer">Diferenciais Unidas</li>
        </ul>
      </div>

      <!-- 2 — COLUNA: A Unidas -->
      <div>
        <h3 class="font-bold mb-4">A LA Veículos </h3>
        <ul class="space-y-2">
          <li class="hover:underline cursor-pointer">Sobre a Unidas</li>
          <li class="hover:underline cursor-pointer">Fale com o Presidente</li>
          <li class="hover:underline cursor-pointer">Trabalhe Conosco</li>
          <li class="hover:underline cursor-pointer">Portal de Privacidade</li>
        </ul>

        <!-- ÍCONES SOCIAIS -->
        <div class="flex gap-4 text-green-700 text-xl mt-4">
          <i class="bi bi-facebook cursor-pointer"></i>
          <i class="bi bi-instagram cursor-pointer"></i>
          <i class="bi bi-youtube cursor-pointer"></i>
          <i class="bi bi-linkedin cursor-pointer"></i>
        </div>
      </div>

      <!-- 3 — COLUNA: Atendimento -->
      <div>
        <h3 class="font-bold mb-4">Atendimento</h3>
        <ul class="space-y-2">
          <li class="hover:underline cursor-pointer">Perguntas Frequentes</li>
          <li class="hover:underline cursor-pointer">Fale Conosco</li>
          <li class="hover:underline cursor-pointer">Ouvidoria</li>
        </ul>

        <button
          class="mt-4 border border-gray-400 px-4 py-2 rounded-md hover:bg-gray-200 transition"
        >
          CONTRATO DE LOCAÇÃO
        </button>
      </div>

      <!-- 4 — COLUNA: Telefones -->
      <div>
        <h3 class="font-bold mb-4">Atendimento ao Cliente</h3>

        <div class="space-y-4">
          <div class="flex items-center gap-3">
            <span class="font-bold text-green-700">0800 771 5158</span>
            <span class="text-green-600 text-2xl"><i class="bi bi-whatsapp"></i></span>
          </div>

          <div>
            <h4 class="font-bold">Central de Reservas 24h</h4>
            <div class="flex items-center gap-3">
              <span class="font-bold text-green-700">0800 6 121 121</span>
              <span class="text-green-600 text-2xl"><i class="bi bi-whatsapp"></i></span>
            </div>
          </div>

          <div>
            <h4 class="font-bold">Central de Assistência 24h</h4>
            <span class="font-bold text-green-700 block">0800 779 4042</span>
          </div>
        </div>
      </div>

    </div>
  </footer>
</template>

<script setup></script>

<style>
@import "https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.1/font/bootstrap-icons.css";
</style>
