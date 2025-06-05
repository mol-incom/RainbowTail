<script setup lang="ts">
import Palette from "@/palette/Palette.vue";
// Generate styles on runtime to make dynamic classes work.
import '@tailwindcss/browser';

const bases = [
  'red',
  'orange',
  'amber',
  'yellow',
  'lime',
  'green',
  'emerald',
  'teal',
  'cyan',
  'sky',
  'blue',
  'indigo',
  'violet',
  'purple',
  'fuchsia',
  'pink',
  'rose',
  'slate',
  'gray',
  'zinc',
  'neutral',
  'stone',
];
const steps = [50, 100, 200, 300, 400, 500, 600, 700, 800, 900, 950];
</script>

<template>
  <div class="flex justify-center">
    <div class="w-6xl">
      <header class="text-4xl font-bold text-center py-8">
        RainbowTail
      </header>
      <main class="flex justify-center">
        <Palette :bases="bases" :steps="steps"/>
      </main>
    </div>
  </div>
</template>
