<script setup>
import { useCounterStore } from "./store/counterStore"

const { locale } = useI18n()
const colorMode = useColorMode()
console.log(colorMode.preference)

const counterStore = useCounterStore()
</script>

<template>
  <div>
    <div>
      <form>
        <select v-model="locale">
          <option value="en">en</option>
          <option value="fr">fr</option>
        </select>
        <p>{{ $t("welcome") }}</p>
      </form>
    </div>
    <div>
      <h1>Color mode: {{ $colorMode.value }}</h1>
      <select v-model="$colorMode.preference">
        <option value="system">System</option>
        <option value="light">Light</option>
        <option value="dark">Dark</option>
        <option value="sepia">Sepia</option>
      </select>
    </div>
    <div>
      <h1>Counter: {{ counterStore.count }}</h1>
      <button @click="counterStore.increment">Increment</button>
    </div>
    <NuxtWelcome />
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
