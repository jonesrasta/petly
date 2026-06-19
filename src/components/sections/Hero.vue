<template>
  <section id="inicio"
    class="relative overflow-hidden min-h-140 md:min-h-screen py-16 md:py-0"
  >
    <!-- Desktop -->
    <img
      src="/pets.png"
      alt="Pets"
      class="absolute inset-0 hidden md:block w-full h-full object-cover"
    />

    <!-- Mobile -->
    <img
      src="/pets-mobile.png"
      alt="Pets"
      class="absolute inset-0 block md:hidden w-full h-170 object-cover object-top"
    />

    <!-- Overlay apenas mobile -->
    <div
      class="absolute inset-0 md:hidden bg-linear-to-b
      from-white/10 via-white/25 to-[#003B53]/10"
    ></div>

    <!-- Conteúdo -->
    <div class="relative z-10 flex items-center min-h-120 md:min-h-screen">
      <div class="mx-auto w-full max-w-7xl px-6 sm:px-8 lg:px-12">
        <div class="max-w-xl mt-18">

          <h1 class="uppercase font-sirage leading-[0.9] text-5xl md:text-7xl">

            <span
              class="block text-[#003B53]
              "
            >
              Tudo o que
            </span>

            <span
              class="block text-[#FF4456]"
            >
              seu pet
            </span>

            <span
              class="block text-[#003B53]"
            >
              precisa.
            </span>

          </h1>

          <p
            class="
              mt-7
              w-80
              md:max-w-md
              text-[#003B53]
              text-[22px]
              md:text-2xl
              italic
              leading-tight
              font-miguer
              font-medium
            "
          >
            Cuidado, carinho e qualidade para cada momento.
            Porque seu melhor amigo merece o melhor.
          </p>

          <div
            class="
              mt-10
              flex
              gap-5
              sm:items-center
            "
          >

            <button
              class="
                relative
                w-35
                h-13
                hover:scale-105
                transition-transform
              "
            >
              <svg
                class="absolute inset-0 w-full h-full"
                viewBox="0 0 140 54"
              >
                <path
                  d="M8 4
                  H122
                  Q132 4 134 10
                  L140 42
                  Q140 50 132 50
                  L18 54
                  Q8 54 6 46
                  L0 12
                  Q0 4 8 4Z"
                  fill="#FF4757"
                />
              </svg>

              <a
              href="#contato"
                class="absolute inset-0 flex items-center justify-center text-white font-miguer font-medium text-lg"
              >
                Contato
            </a>
            </button>

            <a
              href="#sobre"
              class="
                text-[#003B53]
                text-lg
                font-semibold
                md:mt-0
                mt-3
                font-miguer
              "
            >
              Sobre Nós
            </a>

          </div>

        </div>
      </div>
    </div>
  </section>
</template>