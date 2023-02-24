<script setup>
const basedOnList = [
  {
    title: "Nuxt 3",
    link: "https://nuxt.com/",
  },
  {
    title: "Tailwind CSS",
    link: "https://tailwindcss.com/",
  },
  {
    title: "Nuxt Auth",
    link: "https://auth.nuxtjs.org/",
  },
  {
    title: "Pinia",
    link: "https://pinia.esm.dev/",
  },
  {
    title: "Nuxt Icons",
    link: "https://github.com/gitFoxCode/nuxt-icons",
  },
  {
    title: "I18n",
    link: "https://sidebase.io/nuxt-auth/",
  },
  {
    title: "VueUse",
    link: "https://vueuse.org/",
  },
  {
    title: "Color Mode",
    link: "https://color-mode.nuxtjs.org/",
  },
];
</script>

<template>
  <div
    class="min-h-screen py-2 dark:bg-gray-900 sepia:bg-gray-200 dark:text-white"
  >
    <div
      class="justify-center py-2 xl:mt-28 lg:mt-20 md:mt-12 sm:mt-8 mt-4 xl:px-30 lg:px-20 md:px-10 sm:px-5 px-2 mx-auto text-center"
    >
      <h1
        class="xl:text-9xl lg:text-7xl md:text-5xl sm:text-3xl text-3xl font-bold dark:text-white"
      >
        LB Nuxt 3 Template
      </h1>
      <p class="mt-20 text-2xl font-thin text-gray-700 dark:text-gray-300">
        This template is here thanks to the awesome work of the following
        projects
      </p>
      <ul
        class="mt-10 text-2xl font-bold text-gray-700 dark:text-gray-300 grid xl:grid-cols-3 lg:grid-cols-3 md:grid-cols-2 sm:grid-cols-1 cols-1 xl:px-96 lg:px-16 px-7 xl:gap-5 lg:gap-4 md:gap-3 sm:gap-5 gap-5"
      >
        <a
          v-for="item in basedOnList"
          :key="item.title"
          :href="item.link"
          target="_blank"
          class="border-2 p-10 rounded-xl cursor-pointer hover:bg-gray-200 dark:hover:bg-gray-700 sepia:hover:bg-gray-300 hover:border-gray-400 dark:hover:border-gray-600 sepia:hover:border-gray-400 hover:shadow-lg dark:hover:shadow-lg sepia:hover:shadow-lg transition duration-500 ease-in-out transform hover:-translate-y-1 hover:scale-110 dark:hover:scale-110 sepia:hover:scale-110 dark:hover:translate-y-1 sepia:hover:translate-y-1"
        >
          <li>{{ item.title }}</li>
        </a>
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
