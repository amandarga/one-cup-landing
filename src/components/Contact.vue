<template>
  <section class="bg-green-100 text-green-900 py-16 px-6 md:px-20">
    <div class="max-w-3xl mx-auto text-center">
      <h2 class="text-3xl md:text-4xl font-bold mb-6">Teste grátis por 14 dias</h2>
      <p class="text-lg text-green-800 mb-8">
        Preencha os dados abaixo para receber o link de acesso gratuito ao sistema OneCup.
      </p>

      <form
        @submit.prevent="handleSubmit"
        class="bg-white rounded-xl shadow-md p-8 text-left space-y-6"
      >
        <div>
          <label class="block text-sm font-semibold mb-1">Nome completo</label>
          <input
            v-model="form.name"
            type="text"
            required
            class="w-full border border-green-300 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-green-500"
          />
        </div>

        <div>
          <label class="block text-sm font-semibold mb-1">Nome da cafeteria</label>
          <input
            v-model="form.business"
            type="text"
            required
            class="w-full border border-green-300 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-green-500"
          />
        </div>

        <div>
          <label class="block text-sm font-semibold mb-1">E-mail</label>
          <input
            v-model="form.email"
            type="email"
            required
            class="w-full border border-green-300 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-green-500"
          />
        </div>

        <div>
          <label class="block text-sm font-semibold mb-1">WhatsApp</label>
          <input
            v-model="form.whatsapp"
            type="tel"
            required
            placeholder="(xx) xxxxx-xxxx"
            class="w-full border border-green-300 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-green-500"
          />
        </div>

        <button
          type="submit"
          class="w-full bg-green-600 hover:bg-green-700 text-white text-lg font-semibold py-3 px-6 rounded-xl transition-all duration-200"
        >
          ✅ Quero testar grátis
        </button>
      </form>

      <p v-if="submitted" class="text-green-800 font-semibold mt-6">
        Obrigado! Em breve entraremos em contato com seu link de acesso. ☕
      </p>
    </div>
  </section>
</template>

<script setup>
import { reactive, ref } from 'vue'

const form = reactive({
  name: '',
  business: '',
  email: '',
  whatsapp: '',
})

const submitted = ref(false)

function handleSubmit() {
  // Simulação de envio – substituir futuramente por envio real com backend
  console.log('Form enviado:', form)
  submitted.value = true

  // Resetar o formulário depois de enviar
  form.name = ''
  form.business = ''
  form.email = ''
  form.whatsapp = ''
}
</script>
