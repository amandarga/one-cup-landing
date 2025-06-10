<template>
  <section class="bg-white text-[#622d09] py-16 px-6 md:px-20">
    <div class="max-w-6xl mx-auto text-center">
      <h2 class="text-3xl md:text-4xl font-bold mb-10">O que estão dizendo sobre o OneCup?</h2>

      <div class="relative">
        <!-- Slider -->
        <div
          ref="sliderRef"
          class="keen-slider group overflow-hidden"
          @mouseenter="pause = true"
          @mouseleave="pause = false"
        >
          <div
            v-for="(testimonial, index) in testimonials"
            :key="index"
            class="keen-slider__slide px-4 min-w-0"
          >
            <div
              class="h-72 bg-[#622d09] rounded-xl shadow-md p-10 flex flex-col justify-between items-center text-center mx-auto"
            >
              <img
                :src="testimonial.image"
                :alt="testimonial.name"
                class="w-16 h-16 rounded-full object-cover mb-4 border-2 border-[#dcbda5]"
              />
              <p class="text-sm italic text-white mb-4">“{{ testimonial.comment }}”</p>
              <div>
                <p class="text-base text-[#c46233] font-semibold">{{ testimonial.name }}</p>
                <p class="text-sm font-bold text-[#dcbda5]">{{ testimonial.role }}</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Navigation buttons -->
        <button
          @click="slider?.prev()"
          class="absolute left-0 top-1/2 -translate-y-1/2 bg-orange-500 text-white p-2 rounded-full shadow-md hover:bg-orange-700 z-10"
        >
          ⟨
        </button>
        <button
          @click="slider?.next()"
          class="absolute right-0 top-1/2 -translate-y-1/2 bg-orange-500 text-white p-2 rounded-full shadow-md hover:bg-orange-700 z-10"
        >
          ⟩
        </button>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted, nextTick } from 'vue'
import KeenSlider, { KeenSliderInstance } from 'keen-slider'
import 'keen-slider/keen-slider.min.css' // Importante: CSS da KeenSlider

const sliderRef = ref<HTMLDivElement | null>(null)
const slider = ref<KeenSliderInstance | null>(null)
const pause = ref(false)

let interval: ReturnType<typeof setInterval>

onMounted(async () => {
  await nextTick()

  if (sliderRef.value) {
    slider.value = new KeenSlider(sliderRef.value, {
      loop: true,
      slides: {
        perView: 1,
        spacing: 16,
      },
      breakpoints: {
        '(min-width: 640px)': {
          slides: { perView: 2, spacing: 16 },
        },
        '(min-width: 1024px)': {
          slides: { perView: 3, spacing: 16 },
        },
      },
    })

    interval = setInterval(() => {
      if (!pause.value) slider.value?.next()
    }, 4000)
  }
})

onUnmounted(() => {
  slider.value?.destroy()
  clearInterval(interval)
})

const testimonials = [
  {
    comment: 'Desde que começamos a usar o OneCup, o atendimento ficou muito mais fluido.',
    name: 'Carlos Mendes',
    role: 'Dono da Café da Praça',
    image: 'https://i.pravatar.cc/150?img=12',
  },
  {
    comment: 'Os clientes adoram reservar pelo celular. É rápido, fácil e prático.',
    name: 'Renata Alves',
    role: 'Gerente de cafeteria',
    image: 'https://i.pravatar.cc/150?img=47',
  },
  {
    comment: 'Nunca mais ouvi reclamações sobre filas longas.',
    name: 'João Vitor',
    role: 'Barista',
    image: 'https://i.pravatar.cc/150?img=65',
  },
  {
    comment: 'A interface é linda e simples, mesmo quem não é muito tecnológico consegue usar.',
    name: 'Larissa Souza',
    role: 'Cliente frequente',
    image: 'https://i.pravatar.cc/150?img=32',
  },
  {
    comment: 'Sistema leve, intuitivo e estável. Recomendo!',
    name: 'Bruno Costa',
    role: 'Proprietário de franquia',
    image: 'https://i.pravatar.cc/150?img=8',
  },
]
</script>
