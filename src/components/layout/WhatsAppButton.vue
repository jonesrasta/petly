<script setup lang="ts">
import { Icon } from "@iconify/vue";

const whatsappNumber = "5511999999999";
const message = "Olá! Gostaria de agendar uma consulta.";

const whatsappLink = `https://wa.me/${whatsappNumber}?text=${encodeURIComponent(
  message
)}`;
</script>

<template>
  <a
    :href="whatsappLink"
    target="_blank"
    rel="noopener noreferrer"
    class="group fixed bottom-6 right-6 z-40 flex h-14 w-14 items-center justify-center rounded-full bg-[#F6424F] text-white shadow-lg transition-all duration-300 hover:scale-110"
  >
    <Icon
      icon="iconoir:message-solid"
      class="text-2xl"
    />
  </a>
</template>