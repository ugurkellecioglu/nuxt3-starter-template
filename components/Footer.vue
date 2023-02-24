<template>
  <footer
    class="text-center border-t-2 border-gray-100 dark:border-gray-600 text-white dark:bg-gray-900 sepia:bg-gray-200 dark:text-gray-100"
  >
    <div class="container px-6 pt-6 m-auto">
      <div class="flex justify-center mb-6">
        <a
          v-for="link in socials"
          :key="link"
          href="#!"
          type="button"
          class="rounded-full border-2 border-gray-200 dark:border-gray-400 text-gray-500 dark:text-gray-400 leading-normal uppercase hover:bg-black hover:bg-opacity-5 focus:outline-none focus:ring-0 transition duration-150 ease-in-out w-9 h-9 m-1 flex items-center justify-center"
        >
          <NuxtIcon
            :name="`social/${link}`"
            class="w-3 h-full mx-auto flex items-center justify-center"
          />
        </a>
        <ColorSwitchBox />
      </div>
    </div>

    <div class="text-center p-4 text-gray-500 dark:text-gray-400">
      <p>Made with ❤️</p>
      <p>
        Licensed under the <a href="https://opensource.org/licenses/MIT">MIT</a>
      </p>
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
