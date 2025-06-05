<script setup lang="ts">
const {base, step} =defineProps<{
  base: string;
  step: number;
}>()

const color = `bg-${base}-${step}`;
</script>

<template>
  <div :class="color" class="w-10 h-10" :title="color"/>
</template>
