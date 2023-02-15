<script setup>
import { useCounterStore } from "@/store/counterStore"
import { useClipboard, usePermission } from "@vueuse/core"
const { status, data, signOut, signIn } = useSession()

const { locale } = useI18n()
const colorMode = useColorMode()
console.log(colorMode.preference)

const counterStore = useCounterStore()

const input = ref("")
const { text, isSupported, copy } = useClipboard()
const permissionRead = usePermission("clipboard-read")
const permissionWrite = usePermission("clipboard-write")

const basedOnList = [
  {
    title: "Nuxt 3",
    link: "https://v3.nuxtjs.org/",
  },
  {
    title: "Color Mode",
    link: "https://vueuse.org/core/colorMode/",
  },
  {
    title: "Vueuse",
    link: "https://vueuse.org/",
  },
  {
    title: "I18n",
    link: "https://vueuse.org/core/i18n/",
  },
  {
    title: "Nuxt Auth",
    link: "https://auth.nuxtjs.org/",
  },
  {
    title: "Tailwind CSS",
    link: "https://tailwindcss.com/",
  },
  {
    title: "Pinia",
    link: "https://pinia.esm.dev/",
  },
]
</script>

<template>
  <div
    class="min-h-screen py-2 dark:bg-gray-900 sepia:bg-gray-200 dark:text-white"
  >
    <div class="justify-center py-2 mt-40 px-40 mx-auto text-center">
      <h1 class="text-9xl font-bold dark:text-white">LB Nuxt 3 Template</h1>
      <p class="mt-20 text-2xl font-bold text-gray-700 dark:text-gray-300">
        This template is based on:
      </p>
      <ul
        class="mt-10 text-2xl font-bold text-gray-700 dark:text-gray-300 grid grid-cols-2"
      >
        <li v-for="item in basedOnList">
          <a :href="item.link" target="_blank">{{ item.title }}</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<style>
body {
  background-color: #fff;
  color: rgba(0, 0, 0, 0.8);
}
.dark-mode body {
  background-color: #091a28;
  color: #ebf4f1;
}
.sepia-mode body {
  background-color: #f1e7d0;
  color: #433422;
}
</style>
