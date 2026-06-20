<script setup lang="ts">
defineProps<{
  isOpen: boolean
}>()

const emit = defineEmits(["close"])
</script>

<template>
  <Transition name="fade">
    <div
      v-if="isOpen"
      class="fixed inset-0 z-999 flex items-center overflow-x-hidden justify-center font-miguer bg-black/50 backdrop-blur-xs p-4"
    >
      <div
        class="
          relative
          w-full
          max-w-3xl
          rounded-3xl
          bg-[#F4F1EB]/90 
          p-8
          shadow-2xl
          max-h-[90vh]
          overflow-y-auto
          pet-scroll
        "
      >
        <!-- Fechar -->
        <button
          @click="emit('close')"
          class="
            absolute
            top-3
            right-5
            text-[#003B53]
            text-3xl
            font-bold
          "
        >
          ×
        </button>

        <!-- Header -->
        <div class="mb-10">
          <h2
            class="
              text-[#003B53]
              text-3xl
              md:text-4xl
              italic
              font-bold
              font-miguer
              mt-4
            "
          >
            Agendar Atendimento
          </h2>

          <p
            class="
              mt-3
              text-[#7F9198]
              text-lg
            "
          >
            Preencha os dados abaixo para reservar o horário do seu pet.
          </p>
        </div>

        <!-- Form -->
        <form class="space-y-8">

          <!-- Tutor -->
          <div>
            <h3
              class="
                text-[#003B53]
                font-bold
                mb-4
                text-xl
              "
            >
              Dados do Tutor
            </h3>

            <div class="grid md:grid-cols-2 gap-4">

              <input
                type="text"
                placeholder="Nome completo"
                class="pet-input"
              />

              <input
                type="tel"
                placeholder="WhatsApp"
                class="pet-input"
              />

              <input
                type="email"
                placeholder="E-mail"
                class="pet-input md:col-span-2"
              />

            </div>
          </div>

          <!-- Pet -->
          <div>
            <h3
              class="
                text-[#003B53]
                font-bold
                mb-4
                text-xl
              "
            >
              Dados do Pet
            </h3>

            <div class="grid md:grid-cols-2 gap-4">

              <input
                type="text"
                placeholder="Nome do pet"
                class="pet-input"
              />

              <select class="pet-input">
                <option>Cachorro</option>
                <option>Gato</option>
              </select>

              <input
                type="text"
                placeholder="Raça"
                class="pet-input"
              />

              <input
                type="text"
                placeholder="Porte"
                class="pet-input"
              />

              <input
                type="number"
                placeholder="Idade"
                class="pet-input"
              />

            </div>
          </div>

          <!-- Serviço -->
          <div>
            <h3
              class="
                text-[#003B53]
                font-bold
                mb-4
                text-xl
              "
            >
              Agendamento
            </h3>

            <div class="grid md:grid-cols-2 gap-4">

              <select class="pet-input">
                <option>Banho</option>
                <option>Tosa</option>
                <option>Banho & Tosa</option>
                <option>Consulta</option>
              </select>

              <input
                type="date"
                class="pet-input"
              />

              <input
                type="time"
                class="pet-input"
              />

            </div>

            <textarea
              rows="4"
              placeholder="Observações"
              class="pet-input mt-4 resize-none"
            />
          </div>

          <!-- CTA -->
          <div class="pt-2">
            <button
              type="submit"
              class="
                relative
                w-35
                h-15
                hover:scale-105
                transition
              "
            >
              <svg
                class="absolute inset-0 w-full h-full"
                viewBox="0 0 160 60"
              >
                <path
                  d="
                  M10 4
                  H140
                  Q150 4 152 10
                  L160 46
                  Q160 56 150 56
                  L24 60
                  Q10 60 8 50
                  L0 14
                  Q0 4 10 4Z
                "
                  fill="#FF4456"
                />
              </svg>

              <span
                class="
                  absolute
                  inset-0
                  flex
                  items-center
                  justify-center
                  text-white
                  font-semibold
                "
              >
                Agendar
              </span>
            </button>
          </div>

        </form>
      </div>
    </div>
  </Transition>
</template>


<style scoped>
.pet-input {
  width: 100%;
  background: transparent;
  border: 1px solid rgba(0, 61, 79, 0.2);
  border-radius: 14px;
  padding: 10px 14px;
  color: #003b53;
  outline: none;
}

.pet-input:focus {
  border-color: #008cb5;
}

.fade-enter-active,
.fade-leave-active {
  transition: all .25s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.pet-scroll::-webkit-scrollbar {
  width: 6px;
}

.pet-scroll::-webkit-scrollbar-track {
  background: transparent;
}

.pet-scroll::-webkit-scrollbar-thumb {
  background: linear-gradient(
    180deg,
    #008cb5,
    #003d4f
  );
  border-radius: 999px;
}

.pet-scroll::-webkit-scrollbar-thumb:hover {
  background: #003b53;
}

/* Firefox */
.pet-scroll {
  scrollbar-width: thin;
  scrollbar-color: #f6424e8c transparent;
}

</style>