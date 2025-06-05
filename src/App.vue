<script setup lang="ts">
import Palette from "@/palette/Palette.vue";
// Generate styles on runtime to make dynamic classes work.
import '@tailwindcss/browser';
import {useMouse} from "@/useMouse.ts";
import {ref} from "vue";

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

const {x, y} = useMouse();

const colorCode = ref('#666');
</script>

<template>
  <div class="flex justify-center">
    <div
        id="overlay"
        class="h-15 w-15 absolute"
        :style="{top: `${y+1}px`, left: `${x+1}px`, backgroundColor: colorCode}"
    />
    <div class="w-6xl">
      <header class="text-4xl font-bold text-center py-8">
        RainbowTail
      </header>
      <main class="flex justify-center">
        <div>
          <div>
            Overlay Color:
            <input
                v-model="colorCode"
                type="text"
                class="border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-blue-400 text-lg mb-4 w-40 text-center shadow-sm transition"
            />
          </div>
          <Palette :bases="bases" :steps="steps"/>
        </div>
      </main>
    </div>
  </div>
</template>

<style>
#overlay {
  visibility: hidden;
}

:has(#palette:hover) #overlay {
  visibility: visible;
}
</style>
