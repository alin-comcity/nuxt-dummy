<template>
  <section class="bg-gray-100 text-gray-800">
    <div class="max-w-7xl mx-auto px-4 py-12" v-if="product">
      <!-- breadcrum -->
      <div class="text-sm text-gray-600 flex items-center gap-2 mb-4">
        <NuxtLink to="/" class="text-blue-600 hover:underline">Home</NuxtLink>
        <span>/</span>
        <NuxtLink
          :to="`/${product.category?.slug}`"
          class="text-blue-600 hover:underline"
        >
          {{ product.category?.name }}
        </NuxtLink>
        <span>/</span>
        <span class="font-semibold text-gray-800">{{ product.name }}</span>
      </div>
      <!-- /breadcrum -->

      <div
        class="flex flex-col lg:flex-row gap-10 bg-white p-6 rounded-2xl shadow-lg"
      >
        <!-- LEFT: Main Image + Thumbnails -->
        <div class="lg:w-1/2 w-full">
          <!-- Main Image -->
          <img
            :src="selectedImage"
            alt="Selected Product Image"
            class="w-full h-[400px] object-cover rounded-xl shadow transition-all duration-300"
          />

          <!-- Thumbnails -->
          <div class="flex mt-4 space-x-4">
            <img
              v-for="(item, index) in galleryImages"
              :key="index"
              :src="item"
              @click="selectedImage = item"
              class="w-20 h-20 object-cover rounded-lg border-2 cursor-pointer hover:border-green-500"
              :class="{
                'border-green-600': selectedImage === item,
                'border-gray-300': selectedImage !== item,
              }"
            />
          </div>
        </div>

        <!-- RIGHT: Product Info -->
        <div class="lg:w-1/2 w-full flex flex-col justify-between">
          <div>
            <h2 class="text-sm text-gray-500 tracking-widest mb-1">
              {{ product.brands }}
            </h2>
            <h1 class="text-3xl font-bold text-gray-900 mb-4">
              {{ product.name }}
            </h1>
            <p class="text-green-600 text-2xl font-semibold mb-4">
              Tk. {{ product.api.retailprice }}
            </p>
            <p class="leading-relaxed text-gray-700 mb-6 whitespace-pre-line">
              {{ strippedShort }}
            </p>

            <div class="mb-5 text-2xl">
              Category: {{ product.category.name }}
            </div>
          </div>
        </div>
      </div>

      <!-- BELOW: Tabs Section -->
      <div class="mt-10 bg-white p-6 rounded-xl shadow">
        <!-- Tab Headers -->
        <div class="flex space-x-6 border-b">
          <button
            v-for="tab in tabs"
            :key="tab"
            @click="activeTab = tab"
            class="py-2 px-4 text-sm font-semibold border-b-2"
            :class="{
              'border-green-600 text-green-600': activeTab === tab,
              'border-transparent text-gray-500 hover:text-gray-700':
                activeTab !== tab,
            }"
          >
            {{ tab }}
          </button>
        </div>

        <!-- Tab Contents -->
        <div class="mt-6 text-gray-700 whitespace-pre-line">
          <div v-if="activeTab === 'Specification'">
            <div v-html="product.specification"></div>
          </div>
          <div v-else-if="activeTab === 'Description'">
            <div v-html="product.details"></div>
          </div>
          <div v-else-if="activeTab === 'Download'">
            <div
              v-for="(datasheet, idx) in product.datasheet"
              :key="idx"
              class="mb-4"
            >
              <div
                v-for="(datasheet, idx) in product.datasheet"
                :key="idx"
                class="mb-4"
              >
                <a
                  :href="datasheet.src"
                  download
                  class="inline-block bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded transition duration-300"
                >
                  {{ product.brands }}/Datasheet {{ idx + 1 }}
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, watchEffect, computed } from "vue";
import { useRoute } from "vue-router";

const route = useRoute();
const selectedImage = ref("");
const galleryImages = ref([]);

const { data: product } = await useFetch(
  `https://admindash.comcitybd.com/api/product/${route.params.slug}`
);

watchEffect(() => {
  if (product.value) {
    const main = product.value.photo || "";
    const galleryThumbs =
      product.value.gallery?.map((item) => item.image || item.thumb) || [];
    galleryImages.value = [main, ...galleryThumbs].filter(Boolean);
    selectedImage.value = galleryImages.value[0];
  }
});

const strippedShort = computed(() => {
  const html = product.value?.short || "";
  return html
    .replace(/<\/div>/g, "\n")
    .replace(/<[^>]+>/g, "")
    .trim();
});

const parsedSpecs = computed(() =>
  strippedShort.value
    .split("\n")
    .map((line) => line.trim())
    .filter(Boolean)
);

const tabs = ["Specification", "Description", "Download"];
const activeTab = ref("Specification");
</script>
