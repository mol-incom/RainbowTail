<script setup lang="ts">
import Color from "@/palette/Color.vue";

defineProps<{
  bases: string[],
  steps: number[],
}>();
</script>

<template>
  <div id="palette" class="grid gap-3" :class="`grid-cols-${steps.length}`">
    <template v-for="base in bases" :key="base">
      <template v-for="step in steps" :key="step">
        <Color :base="base" :step="step"/>
      </template>
    </template>
  </div>
</template>
