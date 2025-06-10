<template>
  <section class="bg-white text-green-900 py-16 px-6 md:px-20">
    <div class="max-w-5xl mx-auto text-center">
      <h2 class="text-3xl md:text-4xl font-bold mb-10">O que estão dizendo sobre o OneCup?</h2>

      <div class="overflow-x-auto no-scrollbar">
        <div class="flex gap-6 w-max">
          <div
            v-for="(testimonial, index) in testimonials"
            :key="index"
            class="min-w-[280px] max-w-[300px] bg-green-50 rounded-xl shadow-md p-6 text-left flex flex-col justify-between"
          >
            <p class="text-sm italic mb-4">“{{ testimonial.comment }}”</p>
            <div class="flex items-center gap-3">
              <div class="w-10 h-10 rounded-full bg-green-300 flex items-center justify-center text-white font-bold">
                {{ testimonial.initials }}
              </div>
              <div>
                <p class="text-sm font-semibold">{{ testimonial.name }}</p>
                <p class="text-xs text-green-700">{{ testimonial.role }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const testimonials = [
  {
    comment: 'Desde que começamos a usar o OneCup, o atendimento ficou muito mais fluido.',
    name: 'Carlos Mendes',
    role: 'Dono da Café da Praça',
    initials: 'CM',
  },
  {
    comment: 'Os clientes adoram reservar pelo celular. É rápido, fácil e prático.',
    name: 'Renata Alves',
    role: 'Gerente de cafeteria',
    initials: 'RA',
  },
  {
    comment: 'Nunca mais ouvi reclamações sobre filas longas.',
    name: 'João Vitor',
    role: 'Barista',
    initials: 'JV',
  },
  {
    comment: 'A interface é linda e simples, mesmo quem não é muito tecnológico consegue usar.',
    name: 'Larissa Souza',
    role: 'Cliente frequente',
    initials: 'LS',
  },
  {
    comment: 'Sistema leve, intuitivo e estável. Recomendo!',
    name: 'Bruno Costa',
    role: 'Proprietário de franquia',
    initials: 'BC',
  },
]
</script>

<style scoped>
.no-scrollbar::-webkit-scrollbar {
  display: none;
}
.no-scrollbar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>
