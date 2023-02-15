<script setup lang="ts">
const colorMode = useColorMode();

const changeColorMode = () => {
  colorMode.preference = colorMode.value === "dark" ? "light" : "dark";
};
</script>

<template>
  <label class="relative inline-flex cursor-pointer select-none items-center">
    <div
      class="shadow-card flex h-[36px] w-[70px] px-1 items-center justify-center rounded-full bg-gray-200 dark:bg-gray-800 transition-colors"
    >
      <span
        class="light bg-primary flex h-7 w-9 items-center justify-center bg-white rounded-full dark:bg-gray-800 dark:text-gray-200 text-gray-900"
        @click="changeColorMode"
      >
        <NuxtIcon name="sun" />
      </span>
      <span
        class="dark text-body-color flex h-7 w-9 items-center justify-center dark:text-gray-900 dark:bg-white rounded-full text-gray-900"
        @click="changeColorMode"
      >
        <NuxtIcon name="moon" />
      </span>
    </div>
  </label>
</template>

<style scoped></style>
