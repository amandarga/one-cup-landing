<template>
  <section class="bg-coffe-dark text-white py-16 px-6 md:px-20">
    <div class="max-w-3xl mx-auto">
      <h2 class="text-3xl md:text-4xl font-bold text-center mb-10">Como funciona?</h2>
      <p class="text-center text-lg text-orange-100 mb-12">
        Entenda cada etapa da experiência com o OneCup.
      </p>

      <div class="flex flex-col gap-4">
        <div
          v-for="(step, index) in steps"
          :key="index"
          class="bg-white text-green-900 rounded-xl shadow-md overflow-hidden transition-all duration-300"
        >
          <button
            class="w-full flex items-center justify-between px-6 py-4 text-left hover:bg-green-50 transition-colors"
            @click="toggleStep(index)"
          >
            <div class="flex items-center gap-4">
              <div class="text-2xl">{{ step.icon }}</div>
              <h3 class="font-semibold text-lg">{{ step.title }}</h3>
            </div>
            <div class="text-xl text-green-700">
              {{ activeStep === index ? '–' : '+' }}
            </div>
          </button>

          <div
            v-if="activeStep === index"
            class="px-6 pb-6 text-sm text-green-800"
          >
            <p class="mb-2">{{ step.description }}</p>
            <ul class="list-disc ml-5 space-y-1">
              <li v-for="(detail, i) in step.details" :key="i">
                {{ detail }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'


const activeStep = ref(null)

function toggleStep(index) {
  activeStep.value = activeStep.value === index ? null : index
}

const steps = [
  {
    icon: '📱',
    title: '1. Acesso rápido',
    description: 'O cliente entra no site/app e escolhe sua opção.',
    details: [
      'Visualiza tempo estimado de espera',
      'Escolhe entre entrar na fila ou fazer reserva',
      'Preenche dados básicos (nome, quantidade de pessoas)'
    ]
  },
  {
    icon: '📩',
    title: '2. Confirmação',
    description: 'O sistema envia uma confirmação instantânea.',
    details: [
      'Horário reservado ou número da senha virtual',
      'Link de acesso para acompanhar a posição na fila',
      'Opção de cancelamento ou reagendamento'
    ]
  },
  {
    icon: '☕',
    title: '3. Atendimento tranquilo',
    description: 'Cliente comparece no horário e é atendido sem esperar.',
    details: [
      'Barista recebe notificação da chegada',
      'O atendimento segue com fluidez',
      'Cliente avalia a experiência (opcional)'
    ]
  }
]
</script>

<style>
.bg-coffe-dark {
  background-image: url('/src/assets/One-Cup-bg-dark.png');
  background-size: cover;
  background-repeat: no-repeat;
}
</style>
