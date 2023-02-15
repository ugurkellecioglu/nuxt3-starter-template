<template>
  <footer class="text-center bg-gray-900 text-white">
    <div class="container px-6 pt-6">
      <div class="flex justify-center mb-6">
        <a
          v-for="link in socials"
          href="#!"
          type="button"
          class="rounded-full border-2 border-white text-white leading-normal uppercase hover:bg-black hover:bg-opacity-5 focus:outline-none focus:ring-0 transition duration-150 ease-in-out w-9 h-9 m-1"
        >
          <NuxtIcon :name="`social/${link}`" class="w-3 h-full mx-auto" />
        </a>
      </div>
    </div>

    <div class="text-center p-4">
      © {{ new Date().getFullYear() }} Copyright:
      <a
        class="text-whitehite"
        href="https://www.linkedin.com/in/ugurkellecioglu/"
        >Uğur Kellecioğlu</a
      >
    </div>
  </footer>
</template>

<script lang="ts" setup>
type Social =
  | "facebook"
  | "twitter"
  | "google"
  | "instagram"
  | "linkedin"
  | "github";

const socials: Social[] = [
  "facebook",
  "twitter",
  "google",
  "instagram",
  "linkedin",
  "github",
];
</script>
