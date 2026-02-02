<template>
  <section class="text-gray-600 body-font">
    <div class="container px-5 py-24 mx-auto">
      <!-- breadcrum -->
      <div class="text-sm text-gray-600 flex items-center gap-2 mb-4">
        <NuxtLink to="/" class="text-blue-600 hover:underline">Home</NuxtLink>
        <span>/</span>
        <span class="font-semibold text-gray-800">{{ brandName }}</span>
      </div>
      <!-- /breadcrum -->
      <div class="flex flex-wrap -m-4">
        <!-- product 1 -->
        <div
          class="lg:w-1/4 md:w-1/2 p-4 w-full"
          v-for="product in products"
          :key="product.id"
        >
          <NuxtLink
            :to="`/product/${product.slug}`"
            class="block relative rounded overflow-hidden hover:scale-110"
          >
            <img
              alt="ecommerce"
              :src="product.thumbnail"
              width="256"
              height="256"
            />
          </NuxtLink>
          <div class="mt-4">
            <NuxtLink :to="`/product/${product.slug}`">
              <h2
                class="text-gray-900 dark:text-gray-200 title-font text-lg font-medium"
              >
                {{ product.name }}
              </h2>
              <p class="mt-1">
                <span
                  v-if="product.api.retailprice == 0"
                  class="text-red-600 dark:text-red-500"
                  >Out Of Stock
                </span>
                <span v-else class="text-xl font-bold dark:text-gray-200"
                  >Tk. {{ product.api.retailprice }}</span
                >
              </p>
            </NuxtLink>
          </div>
        </div>
        <!-- end of product 1 -->
      </div>
    </div>
  </section>
</template>

<script setup>
const { data } = await useFetch(
  "https://admindash.comcitybd.com/api/brands/Acer%20Gadget/100?id[]=20"
);
const products = data.value.data;

const brandName = "Casing";
</script>
