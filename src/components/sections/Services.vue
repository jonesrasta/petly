<script setup lang="ts">
import { ShowerHead, Scissors, PawPrint, Stethoscope } from "lucide-vue-next";
</script>

<template>
  <section id="servicos" class="bg-[#F4F1EB] py-4 md:py-24">
    <div class="max-w-7xl mx-auto px-6">

      <!-- Header -->
      <div class="mb-14">
        <h2 class="
            text-[#003B53]
            md:text-5xl
            text-4xl
            font-bold
            italic
            leading-none
            font-miguer
          ">
          Nossos serviços de cuidados
        </h2>

        <p class="
            mt-4
            text-[#7F9198]
            text-xl
            max-w-md
            font-miguer
          ">
          Tudo o que seu pet precisa para se sentir bem,
          bonito e cheio de energia.
        </p>
      </div>

      <!-- Grid -->
      <div class="grid lg:grid-cols-3 gap-10 md:gap-5">

        <!-- Card 1 -->
        <div class="service-card">
          <div class="service-content">

            <div class="flex justify-between items-start mt-2 px-2">
              <img src="/avatar-1.png" alt="" class="w-14 h-14 rounded-full object-cover" />

              <button class="">
                <img src="/arrow.png" alt="" />
              </button>
            </div>

            <div class="mt-auto">
              <h3 class="
                  text-[#003B53]
                  font-medium
                  text-lg
                  px-2
                  font-miguer
                ">
                Tratamentos Especializados
              </h3>
            </div>

          </div>
        </div>

        <!-- Card destaque -->
        <div class="service-card active">

          <div class="service-content p-0 overflow-hidden">

            <img src="/service-premium.png" alt="" class="w-full object-cover" />

            <div class="p-4">

              <h3 class="
                  text-[#003B53]
                  font-medium
                  text-lg
                  mb-4
                  font-miguer
                ">
                Cuidados Premium
                <div class="h-px bg-linear-to-r from-transparent via-[#003D4F]/50 to-transparent mt-2" />
              </h3>


              <ul class="space-y-3 font-miguer">
                <li class="flex items-center gap-2 text-sm text-[#7F9198]">
                  <ShowerHead :size="24" class="text-[#7F9198]" />
                  <span>Banho & Higiene Completa</span>
                </li>

                <li class="flex items-center gap-2 text-sm text-[#7F9198]">
                  <Scissors :size="24" class="text-[#7F9198]" />
                  <span>Tosa Personalizada</span>
                </li>

                <li class="flex items-center gap-2 text-sm text-[#7F9198]">
                  <PawPrint :size="24" class="text-[#7F9198]" />
                  <span>Cuidados Bem-Estar</span>
                </li>

                <li class="flex items-center gap-2 text-sm text-[#7F9198]">
                  <Stethoscope :size="24" class="text-[#7F9198]" />
                  <span>Acompanhamento de Saúde</span>
                </li>
              </ul>

            </div>

          </div>

          <button class="absolute bottom-3 right-3">
            <img src="/arrow.png" alt="" />
          </button>
        </div>

        <!-- Card 3 -->
        <div class="service-card">

          <div class="service-content">

            <div class="flex justify-between items-start mt-2 px-2">
              <img src="/avatar-2.png" alt="" class="w-14 h-14 rounded-full object-cover" />

              <button class="">

                <img src="/arrow.png" alt="arrow-up" />
              </button>
            </div>

            <div class="mt-auto">
              <h3 class="
                  text-[#003B53]
                  font-medium
                  text-lg
                  px-2
                  font-miguer
                ">
                Banho & Tosa
              </h3>
            </div>

          </div>

        </div>

      </div>

    </div>
  </section>
</template>

<style scoped>
.service-card {
  position: relative;

  height: 490px;

  padding: 1px;

  border-radius: 18px;

  background:
    linear-gradient(180deg,
      rgb(0, 139, 181),
      rgba(0, 61, 79, 0));
}

.service-content {
  height: 100%;

  background: #f4f1eb;

  border-radius: 17px;

  padding: 6px;

  display: flex;
  flex-direction: column;
}

.active {
  transform: translateY(2px);
}
</style>