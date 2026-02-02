<template>
  <div class="container mx-auto px-4 py-16 bg-gray-200 dark:bg-gray-700 md:px-24 lg:px-8 lg:py-20">
  <div class="grid gap-10 lg:grid-cols-2">
      <div class="flex flex-col justify-center md:pr-8 lg:max-w-lg xl:pr-0">
        <div class="mb-6 max-w-xl">
          <h2 class="mb-6 max-w-lg font-sans text-3xl font-bold tracking-tight text-black dark:text-white sm:text-4xl sm:leading-none">
            Our Product Line<br class="hidden md:block" />
          </h2>
          <p class="text-base text-gray-600 dark:text-gray-200 md:text-lg">
            We specialize in crossover integration, crafting products, services, and solutions that revolutionize daily life in areas such as clothing, transportation, work and entertainment.
          </p>
        </div>
      </div>
      
      <div class="-mx-4 flex items-center justify-center lg:pl-8">
        <div class="flex flex-col items-end px-3">
          <Image alt="Image" preview class="mb-5">
            <template>
              <i class="pi pi-search"></i>
            </template>
            <template #image>
              <img
                src="/img/ac1000.png"
                format="webp"
                alt="image"
                width="250"
                class="h-20 w-20 rounded object-cover shadow-lg dark:bg-gray-100 sm:h-32 sm:w-32 xl:h-40 xl:w-40"
              />
            </template>
            <template #preview="slotProps">
              <img
                class="h-[90vh]"
                src="/img/ac1000.png"
                format="webp"
                alt="preview"
                sizes="100vw sm:50vw md:1000px"
                :style="slotProps.style"
                click="slotProps.onClick"
              />
            </template>
          </Image>

          <Image alt="Image" preview>
            <template #indicatoricon>
              <i class="pi pi-search"></i>
            </template>
            <template #image>
              <img
                src="/img/1237.jpg"
                format="webp"
                alt="image"
                width="250"
                class="h-20 w-20 rounded object-cover shadow-lg dark:bg-gray-100 sm:h-32 sm:w-32 xl:h-40 xl:w-40"
              />
            </template>
            <template #preview="slotProps">
              <img
                class="h-[90vh]"
                src="/img/1237.jpg"
                format="webp"
                alt="preview"
                sizes="100vw sm:50vw md:1000px"
                :style="slotProps.style"
                click="slotProps.onClick"
              />
            </template>
          </Image>

          <Image alt="Image" preview class="mb-5 mt-5">
            <template>
              <i class="pi pi-search"></i>
            </template>
            <template #image>
              <img
                src="/img/cooling_144_144.jpeg"
                format="webp"
                alt="image"
                width="250"
                class="h-20 w-20 rounded object-cover shadow-lg dark:bg-gray-100 sm:h-32 sm:w-32 xl:h-40 xl:w-40"
              />
            </template>
            <template #preview="slotProps">
              <img
                class="h-[90vh]"
                src="/img/cooling_144_144.jpeg"
                format="webp"
                alt="preview"
                sizes="100vw sm:50vw md:1000px"
                :style="slotProps.style"
                click="slotProps.onClick"
              />
            </template>
          </Image>
        </div>

        <div class="px-3">
          <Image alt="Image" preview>
            <template #indicatoricon>
              <i class="pi pi-search"></i>
            </template>
            <template #image>
              <img
                src="/img/U351.jpg"
                format="webp"
                alt="image"
                width="250"
                class="h-40 w-40 rounded object-cover shadow-lg dark:bg-gray-100 sm:h-64 sm:w-64 xl:h-80 xl:w-80"
              />
            </template>
            <template #preview="slotProps">
              <img
                class="h-[90vh]"
                src="/img/U351.jpg"
                format="webp"
                alt="preview"
                sizes="100vw sm:50vw md:1000px"
                :style="slotProps.style"
                click="slotProps.onClick"
              />
            </template>
          </Image>
        </div>
      </div>
      
    </div>
  </div>
</template>
