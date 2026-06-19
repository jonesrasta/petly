<script setup lang="ts">
import { computed, onMounted, onBeforeUnmount, ref } from "vue";

/* ==========================================
   TYPES
========================================== */

interface Slide {
    id: number;
    title: string;
    image: string;
}

/* ==========================================
   PROPS
========================================== */

const props = withDefaults(
    defineProps<{
        slides: Slide[];
        autoplay?: boolean;
        interval?: number;
    }>(),
    {
        autoplay: true,
        interval: 3500,
    }
);

/* ==========================================
   STATE
========================================== */

const current = ref(0);

const total = computed(() => props.slides.length);

/* ==========================================
   HELPERS
========================================== */

function normalize(index: number) {
    const length = total.value;

    if (!length) return 0;

    return ((index % length) + length) % length;
}

const visibleSlides = computed(() =>
    [
        props.slides[normalize(current.value - 2)],
        props.slides[normalize(current.value - 1)],
        props.slides[normalize(current.value)],
        props.slides[normalize(current.value + 1)],
        props.slides[normalize(current.value + 2)],
    ].filter(Boolean) as Slide[]
);

/* ==========================================
   CAROUSEL ACTIONS
========================================== */

function next() {
    current.value = normalize(current.value + 1);
    restartAutoplay();
}

function prev() {
    current.value = normalize(current.value - 1);
    restartAutoplay();
}

function goTo(position: number) {
    const actions = {
        0: () => {
            prev();
            prev();
        },
        1: () => prev(),
        2: () => { },
        3: () => next(),
        4: () => {
            next();
            next();
        },
    };

    actions[position as keyof typeof actions]?.();
}

/* ==========================================
   CARD POSITIONS
========================================== */

const POSITION_CLASSES = [
    "left-[3%] w-[170px] h-[235px] opacity-30 scale-90 z-10",
    "left-[20%] w-[185px] border-none h-[250px] opacity-30 scale-100 z-20 rounded-3xl",
    "left-1/2 -translate-x-1/2 w-[280px] h-[460px] rounded-4xl border-[8px] border-black shadow-[0_18px_35px_rgba(0,0,0,.22)] z-50",
    "right-[20%] w-[185px] h-[250px] opacity-40 scale-100 z-20 rounded-3xl",
    "right-[3%] w-[170px] h-[235px] opacity-30 scale-90 z-10",
];

function cardClass(index: number) {
    return POSITION_CLASSES[index];
}

/* ==========================================
   AUTOPLAY
========================================== */

let timer: ReturnType<typeof setInterval> | null = null;

function startAutoplay() {
    if (!props.autoplay) return;

    stopAutoplay();

    timer = setInterval(next, props.interval);
}

function stopAutoplay() {
    if (!timer) return;

    clearInterval(timer);
    timer = null;
}

function restartAutoplay() {
    if (!props.autoplay) return;

    stopAutoplay();
    startAutoplay();
}

/* ==========================================
   KEYBOARD
========================================== */

function keyboard(event: KeyboardEvent) {
    if (event.key === "ArrowRight") next();

    if (event.key === "ArrowLeft") prev();
}

/* ==========================================
   DRAG / TOUCH
========================================== */

const startX = ref(0);
const currentX = ref(0);
const dragging = ref(false);

function getClientX(event: MouseEvent | TouchEvent) {
    if (event instanceof TouchEvent) {
        return event.touches[0]?.clientX ?? 0;
    }

    return event.clientX;
}

function startDrag(event: MouseEvent | TouchEvent) {
    dragging.value = true;

    const x = getClientX(event);

    startX.value = x;
    currentX.value = x;

    stopAutoplay();
}

function moveDrag(event: MouseEvent | TouchEvent) {
    if (!dragging.value) return;

    currentX.value = getClientX(event);
}

function endDrag() {
    if (!dragging.value) return;

    const distance = currentX.value - startX.value;

    if (distance > 70) prev();

    if (distance < -70) next();

    dragging.value = false;

    startAutoplay();
}

/* ==========================================
   LIFECYCLE
========================================== */

onMounted(() => {
    startAutoplay();

    window.addEventListener("keydown", keyboard);
});

onBeforeUnmount(() => {
    stopAutoplay();

    window.removeEventListener("keydown", keyboard);
});
</script>

<template>
    <section class="w-full bg-[#F4F1EB] py-16 overflow-hidden select-none">
        <div class="max-w-7xl mx-auto px-6">

            <!-- Título -->
            <h2
                class="md:text-center font-miguer text-[#0D4B63] md:text-5xl text-4xl italic font-semibold tracking-tight mb-16">
                Nossos resultados de cuidados
            </h2>

            <!-- Carousel -->
            <div class="relative flex items-center justify-center h-117.5">
                <div class="relative flex items-center justify-center w-full h-full">

                    <div v-for="(item, index) in visibleSlides" :key="item.id" @click="goTo(index)"
                        :class="cardClass(index)"
                        class="absolute cursor-pointer duration-700 ease-[cubic-bezier(.22,1,.36,1)]">
                        <div class="
    overflow-hidden
    rounded-3xl
    w-full
    h-full
    bg-white
  ">
                            <img :src="item.image" :alt="item.title" class="w-full h-full object-cover">
                        </div>
                    </div>

                </div>
            </div>

            <!-- Ver Mais -->
            <div class="flex justify-center mt-14">
                <button class="group flex items-center gap-3">
                    <span class="text-[#0D4B63] font-miguer font-semibold text-lg">
                        Ver Mais
                    </span>
                    <img src="/button.svg" alt="Sobre  Nós" class="h-6" />
                </button>
            </div>

        </div>
    </section>
</template>
