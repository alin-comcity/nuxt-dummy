<template>

  <section class="text-gray-600 body-font">
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-wrap -m-4">
        <!-- product 1 -->
        <div class="lg:w-1/4 md:w-1/2 p-4 w-full" v-for="product in products" :key="product.id">
          <a :href="`https://comcitybd.com/product/${product.slug}`" target="_blank" class="block relative rounded overflow-hidden hover:scale-110">
            <img alt="ecommerce" :src="product.thumbnail" width="256" height="256" />
          </a>
          <div class="mt-4">
            <a :href="`https://comcitybd.com/product/${product.slug}`" target="_blank">
            <h2 class="text-gray-900 dark:text-gray-200 title-font text-lg font-medium"> {{ product.name }}</h2>
            <p class="mt-1"> <span v-if="product.api.retailprice == 0" class="text-red-600  dark:text-red-500">Out Of Stock </span> <span v-else class="text-xl font-bold dark:text-gray-200">Tk. {{ product.api.retailprice }}</span></p>
            </a>
          </div>
        </div>
        <!-- end of product 1 -->
      </div>
    </div>
  </section>
  
  </template>
  
  <script setup>
  const { data } = await useFetch('https://admindash.comcitybd.com/api/brands/Acer%20Gadget/100?id[]=21');
  const products = data.value.data;
  </script>
  