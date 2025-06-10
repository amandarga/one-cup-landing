<template>
  <section class="bg-coffe text-[#622d09] py-16 px-6 md:px-20">
    <div class="max-w-6xl mx-auto text-center">
      <h2 class="text-3xl md:text-4xl font-bold mb-10">Por que usar o OneCup?</h2>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-10">
        <div
          v-for="(card, index) in cards"
          :key="index"
          class="bg-[#622d09] rounded-2xl shadow-md p-6 flex flex-col items-start text-left hover:shadow-lg transition-shadow duration-300">
          <img :src="card.icon" alt="" class="w-10 h-10 mb-4" />
          <h3 class="font-bold text-[#dcbda5] text-lg mb-2">{{ card.title }}</h3>
          <p class="text-sm text-[white]">{{ card.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import movel from '../assets/botao-movel.png'
import raio from '../assets/parafuso-2.png'
import graficohistograma from '../assets/grafico-histograma.png'
import trancar from '../assets/trancar.png'
import computador from '../assets/computador.png'
import apertodemao from '../assets/aperto-de-mao.png'

const cards = [
  {
    icon: movel,
    title: 'Evita filas e aglomerações',
    description: 'Clientes entram na fila de forma digital, sem espera física.',
  },
  {
    icon: raio,
    title: 'Experiência rápida e moderna',
    description: 'Interface simples, mobile-first e amigável.',
  },
  {
    icon: graficohistograma,
    title: 'Dados em tempo real',
    description: 'Veja reservas, cancelamentos e filas ao vivo.',
  },
  {
    icon: trancar,
    title: 'Segurança e estabilidade',
    description: 'Validação de dados e 99% de uptime.',
  },
  {
    icon: computador,
    title: 'Responsivo e acessível',
    description: 'Funciona bem em todos os dispositivos e navegadores.',
  },
  {
    icon: apertodemao,
    title: 'Fidelização de clientes',
    description: 'Ofereça uma experiência que faz o cliente voltar.',
  },
];
</script>

<style>
.bg-coffe {
  background-image: url('/src/assets/One-Cup-bg.png');
  background-size: cover;
  background-repeat: no-repeat;
}
</style>
