<template>
  <div class="container border-b">
    <MegaMenu :model="items" class="justify-between px-40">
      <template #start>
        <nuxt-link to="/" class="flex">
          <img
            src="/Acer Gadget Logo - eMachine.png"
            width="230px"
            alt="logo"
            class="py-3"
          />
        </nuxt-link>
      </template>

      <template #item="{ item }" class="justify-end">
        <Nuxt-Link
          :to="item.route"
          v-if="item.root"
          class="flex items-center cursor-pointer px-4 py-2 overflow-hidden relative font-semibold text-lg uppercase"
          style="border-radius: 2rem"
        >
          <span>{{ item.label }}</span>
        </Nuxt-Link>
        <Nuxt-Link
          :to="item.route"
          v-else-if="!item.image"
          class="flex items-center p-4 cursor-pointer mb-2 gap-3"
        >
          <span
            class="inline-flex items-center justify-center rounded-full bg-primary text-primary-contrast w-12 h-12"
          >
            <i :class="[item.icon, 'text-lg']"></i>
          </span>
          <span class="inline-flex flex-col gap-1">
            <span class="font-bold text-lg">{{ item.label }}</span>
            <span class="whitespace-nowrap">{{ item.subtext }}</span>
          </span>
        </Nuxt-Link>
        <div v-else class="flex flex-col items-start gap-4 p-2">
          <img alt="megamenu-demo" :src="item.image" class="w-full" />
          <span>{{ item.subtext }}</span>
          <Button :label="item.label" outlined />
        </div>
      </template>
    </MegaMenu>
  </div>
</template>

<style>
.p-megamenu {
  border: none;
  background: none;
}
</style>

<script setup>
import { ref } from "vue";

import { useRouter } from "vue-router";

const router = useRouter();

const items = ref([
  {
    label: "Home",
    root: true,
    route: "/",
  },
  {
    label: "Products",
    root: true,
    route: "#",
    items: [
      [
        {
          items: [
            {
              label: "Casing",
              icon: "pi pi-list",
              route: "/casing",
              subtext: "Casing",
            },
          ],
        },
      ],
      [
        {
          items: [
            {
              label: "Power Supply",
              icon: "pi pi-shield",
              route: "/power-supply",
              subtext: "Subtext of item",
            },
          ],
        },
      ],
      [
        {
          items: [
            {
              label: "Fan",
              icon: "pi pi-comments",
              route: "/cooler-fan",
              subtext: "Subtext of item",
            },
          ],
        },
      ],
      [
        {
          items: [
            {
              label: "Cooling",
              icon: "pi pi-comments",
              route: "/liquid-cooler",
              subtext: "Subtext of item",
            },
          ],
        },
      ],
    ],
  },
  {
    label: "About Us",
    root: true,
    route: "/about",
  },
  {
    label: "Contact",
    root: true,
    route: "/contact",
  },
]);
</script>
