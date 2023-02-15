<template>
  <header
    class="sticky top-0 z-30 lg:relative transition-all duration-[0.4s] ease dark:bg-gray-900 bg-white shadow-sm dark:shadow-none"
  >
    <!---->
    <div class="mx-auto sm:px-6 lg:px-8 px-4 max-w-7xl relative">
      <!--[-->
      <nav
        id="main-nav"
        class="grid items-center h-16 grid-cols-6 gap-3 lg:h-20 lg:justify-center"
        aria-label="Primary Navigation"
      >
        <div
          class="flex justify-center col-span-4 lg:col-span-1 lg:justify-start"
        >
          <a
            href="/"
            class="flex items-center gap-1 dark:text-gray-300 text-gray-600 text-sm lg:text-base"
          >
            <NuxtIcon name="logo" />
            <span class="dark:text-gray-300 text-gray-600 text-sm lg:text-base"
              >LB Nuxt Template</span
            >
          </a>
        </div>
        <ul
          class="justify-center hidden lg:col-span-4 lg:gap-x-8 xl:gap-x-10 lg:flex dark:text-gray-300 text-gray-600"
        >
          <!--[-->
          <li v-for="link in links">
            <NuxtLink
              :to="link.href"
              class="text-sm lg:text-base link font-medium text-gray-600 hover:text-gray-900 focus:text-gray-900 active:shadow-inner active:font-semibold dark:hover:text-gray-300 dark:focus:text-gray-600 dark:active:text-gray-300 dark:text-gray-400 px-4 py-2 rounded-md transition duration-200 ease-in-out dark:hover:bg-gray-700 dark:focus:bg-gray-700 dark:active:bg-gray-700 hover:bg-gray-100 focus:bg-gray-100 active:bg-gray-100"
              >{{ link.text }}</NuxtLink
            >
          </li>
          <!--]-->
        </ul>
        <div class="flex justify-end">
          <NuxtLink
            to="/login"
            class="bg-gray-900 dark:bg-gray-100 text-white dark:text-gray-900 px-4 py-2 rounded font-semibold text-sm lg:text-base transition duration-200 ease-in-out hover:bg-gray-800 dark:hover:bg-gray-200 focus:outline-none focus:ring-2 focus:ring-gray-900 dark:focus:ring-gray-100 focus:ring-opacity-50 dark:focus:ring-opacity-50 focus:ring-offset-2 dark:focus:ring-offset-2 focus:ring-offset-gray-900 dark:focus:ring-offset-gray-100 focus:ring-offset-opacity-50 dark:focus:ring-offset-opacity-50 focus:ring-inset dark:focus:ring-inset focus:ring-offset-inset dark:focus:ring-offset-inset"
          >
            Log In
          </NuxtLink>
        </div>
      </nav>
      <!--]-->
    </div>
  </header>
</template>

<script setup lang="ts">
type HeaderLink = { text: string; href: string };
const links: HeaderLink[] = [
  { text: "Docs", href: "/docs" },
  { text: "Pricing", href: "/pricing" },
  {
    text: "Blog",
    href: "https://nuxtjs.org/blog",
  },
];
</script>
