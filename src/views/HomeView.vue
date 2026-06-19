<script setup lang="ts">
import Header from '@/components/layout/Header.vue';
import About from '@/components/sections/About.vue';
import Hero from '@/components/sections/Hero.vue';
import Services from '@/components/sections/Services.vue';
import CareCarousel from "@/components/sections/Carousel.vue";
import Process from '@/components/sections/Process.vue';
import Footer from '@/components/layout/Footer.vue';
import WhatsAppButton from "@/components/layout/WhatsAppButton.vue";

const slides = [
  {
    id: 1,
    title: "Dog 1",
    image:
      "https://images.unsplash.com/photo-1560807707-8cc77767d783?q=80&w=735&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  },
  {
    id: 2,
    title: "Dog 2",
    image:
      "https://plus.unsplash.com/premium_photo-1661903055250-d4cd3d70f805?q=80&w=880&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  },
  {
    id: 3,
    title: "Dog 3",
    image:
      "https://plus.unsplash.com/premium_photo-1693586733707-1260454b2cbc?q=80&w=627&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  },
  {
    id: 4,
    title: "Dog 4",
    image:
      "https://plus.unsplash.com/premium_photo-1664391969429-759e9c610fb0?q=80&w=754&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  },
  {
    id: 5,
    title: "Dog 5",
    image:
      "https://plus.unsplash.com/premium_photo-1676389281623-bb714b527b50?q=80&w=686&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  },
  {
    id: 6,
    title: "Dog 6",
    image:
      "https://plus.unsplash.com/premium_photo-1668606717900-0ecf91e55655?q=80&w=765&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  },
  {
    id: 7,
    title: "Dog 7",
    image:
      "https://images.unsplash.com/photo-1583337130417-3346a1be7dee?q=80&w=764&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  },
];
</script>






<template>
  <main>
    <Header />
    <Hero />
    <About />
    <Services />
        <CareCarousel
      :slides="slides"
      :autoplay="true"
      :interval="3500"
    />
    <Process />
    <Footer />
    <WhatsAppButton />
  </main>
</template>
