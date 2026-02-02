<template>
  <!-- component -->
  <section>
    <div class="container mx-auto">
      <h1
        class="text-center text-5xl pb-12 text-gray-900 dark:text-white sm:text-4xl"
      >
        Our Products
      </h1>

      <div
        class="grid grid-cols-1 lg:grid-cols-2 xl:grid-cols-4 gap-x-4 gap-y-28 lg:gap-y-16 mt-10 mb-10"
      >
        <div
          class="relative group h-48 flex flex-col rounded-xl bg-clip-border text-gray-800 dark:text-white shadow-md"
        >
          <NuxtLink to="/casing" class="block">
            <div class="h-28">
              <div
                class="absolute -top-20 lg:top-[-10%] left-[5%] z-40 group-hover:top-[-40%] group-hover:opacity-[0.9] duration-300 w-[90%] h-48 bg-white rounded-xl justify-items-center align-middle"
              >
                <img
                  src="/img/Casing_V920.jpg"
                  class="w-36 h-36 mt-6 m-auto"
                  alt="Automotive"
                  title="Automotive"
                  loading="lazy"
                  width="200"
                  height="200"
                />
              </div>
            </div>
            <div class="p-6 z-10 w-full text-gray-700 dark:text-white">
              <p
                class="mb-2 inline-block text-tg text-center w-full text-xl font-sans font-semibold leading-snug tracking-normal antialiased"
              >
                Casing
              </p>
            </div>
          </NuxtLink>
        </div>

        <div
          class="relative group h-48 flex flex-col rounded-xl bg-clip-border text-gray-800 dark:text-white shadow-md"
        >
          <NuxtLink to="/power" class="block">
            <div class="h-28">
              <div
                class="absolute -top-20 lg:top-[-10%] left-[5%] z-40 group-hover:top-[-40%] group-hover:opacity-[0.9] duration-300 w-[90%] h-48 bg-white rounded-xl justify-items-center align-middle"
              >
                <img
                  src="/img/ac1000.png"
                  class="w-36 h-36 mt-6 m-auto"
                  alt="Automotive"
                  title="Automotive"
                  loading="lazy"
                  width="200"
                  height="200"
                />
              </div>
            </div>
            <div class="p-6 z-10 w-full text-gray-700 dark:text-white">
              <p
                class="mb-2 inline-block text-tg text-center w-full text-xl font-sans font-semibold leading-snug tracking-normal antialiased"
              >
                Power Supply
              </p>
            </div>
          </NuxtLink>
        </div>

        <div
          class="relative group h-48 flex flex-col rounded-xl bg-clip-border text-gray-800 dark:text-white shadow-md"
        >
          <NuxtLink to="/cooling" class="block">
            <div class="h-28">
              <div
                class="absolute -top-20 lg:top-[-10%] left-[5%] z-40 group-hover:top-[-40%] group-hover:opacity-[0.9] duration-300 w-[90%] h-48 bg-white rounded-xl justify-items-center align-middle"
              >
                <img
                  src="/img/cooling_144_144.jpeg"
                  class="w-36 h-36 mt-6 m-auto"
                  alt="Automotive"
                  title="Automotive"
                  loading="lazy"
                  width="200"
                  height="200"
                />
              </div>
            </div>
            <div class="p-6 z-10 w-full text-gray-700 dark:text-white">
              <p
                class="mb-2 inline-block text-tg text-center w-full text-xl font-sans font-semibold leading-snug tracking-normal antialiased"
              >
                Liquid Cooler
              </p>
            </div>
          </NuxtLink>
        </div>

        <div
          class="relative group h-48 flex flex-col rounded-xl bg-clip-border text-gray-800 dark:text-white shadow-md"
        >
          <NuxtLink to="/fan" class="block">
            <div class="h-28">
              <div
                class="absolute -top-20 lg:top-[-10%] left-[5%] z-40 group-hover:top-[-40%] group-hover:opacity-[0.9] duration-300 w-[90%] h-48 bg-white rounded-xl justify-items-center align-middle"
              >
                <img
                  src="/img/Cooling.jpg"
                  class="w-36 h-36 mt-6 m-auto"
                  alt="Automotive"
                  title="Automotive"
                  loading="lazy"
                  width="200"
                  height="200"
                />
              </div>
            </div>
            <div class="p-6 z-10 w-full text-gray-700 dark:text-white">
              <p
                class="mb-2 inline-block text-tg text-center w-full text-xl font-sans font-semibold leading-snug tracking-normal antialiased"
              >
                Fan
              </p>
            </div>
          </NuxtLink>
        </div>
      </div>
    </div>
  </section>
</template>
