<template>
  <section class="bg-coffe-dark text-white py-16 px-6 md:px-20">
    <div class="max-w-3xl mx-auto text-center">
      <h2 class="text-3xl md:text-4xl font-bold mb-6">Oferta de lançamento exclusiva</h2>

      <p class="text-lg mb-4 text-white">
        Comece a usar o OneCup agora com um desconto especial para os primeiros parceiros.
      </p>

      <div class="bg-white border border-orange-200 shadow-md rounded-2xl p-8 my-8">
        <p class="text-sm text-green-700 mb-2">Preço original:</p>
        <p class="text-2xl md:text-3xl line-through text-gray-400 mb-2">R$89/mês</p>

        <p class="text-sm text-green-700 mb-2">Preço promocional:</p>
        <p class="text-4xl md:text-5xl text-[#622d09] font-extrabold mb-4">R$39/mês</p>

        <p class="text-green-800 mb-6">Válido para os <strong>50 primeiros clientes</strong> ou até <strong>15 de julho</strong>.</p>

        <button
          class="bg-[#622d09] hover:bg-orange-600 text-white text-lg font-semibold py-3 px-8 rounded-xl shadow-md transition-all duration-200"
        >
          Quero aproveitar essa oferta!
        </button>
      </div>

      <p class="text-sm text-yellow-700 mt-4">
        ⚠️ Oferta por tempo limitado. Garanta agora seu acesso com valor reduzido.
      </p>
    </div>
  </section>
</template>

<script setup>
// Nenhum script necessário por enquanto
</script>

<style>
.bg-coffe-dark {
  background-image: url('/src/assets/One-Cup-bg-dark.png');
  background-size: cover;
  background-repeat: no-repeat;
}
</style>