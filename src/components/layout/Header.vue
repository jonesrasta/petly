<script setup lang="ts">
import { ref } from "vue";
import Scheduling from "@/components/Scheduling.vue";

const openModal = ref(false);
</script>



<template>
    <header class="absolute top-0 left-0 z-50 w-full">
        <div class="mx-auto flex max-w-7xl items-center justify-between px-6 py-4 lg:px-12">
            <!-- Logo -->
            <a href="/" class="flex items-center gap-3">
                <img src="/logo.svg" alt="Petly" class="h-14 w-auto" />
            </a>

            <!-- Navegação -->
            <nav class="hidden lg:flex items-center gap-14 text-[#003B53] font-miguer  font-medium">
                <a href="#inicio">Início</a>
                <a href="#sobre">Sobre</a>
                <a href="#servicos">Serviços</a>
                <a href="#contato">Contato</a>
            </nav>

            <!-- Ações -->
            <div class="flex items-center gap-8">
                <!-- <a href="#" class="hidden sm:block text-[#003B53] font-miguer font-semibold text-lg">
                    Entrar
                </a> -->

                <button @click="openModal = true" class="
          relative
          w-34
          h-13
          hover:scale-105
          transition-transform
        ">
                    <svg class="absolute inset-0 w-full h-full" viewBox="0 0 140 54">
                        <path d="M132 4
            H18
            Q8 4 6 10
            L0 42
            Q0 50 8 50
            L122 54
            Q132 54 134 46
            L140 12
            Q140 4 132 4Z" fill="#FF4757" />
                    </svg>

                    <span class="
            absolute
            inset-0
            flex
            items-center
            justify-center
            text-white
            font-medium
            text-lg
            font-miguer
          ">
                        Agendar
                    </span>
                </button>

                <!-- Modal -->
                <Scheduling :isOpen="openModal" @close="openModal = false" />
            </div>
        </div>
    </header>
</template>
