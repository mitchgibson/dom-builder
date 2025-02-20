<template>

<div class="h-full w-full relative bg-gray-800 text-gray-400">
  <ElementsMenu class="absolute bottom-5 left-1/2 -translate-x-1/2 min-w-40 h-12 border border-gray-600 rounded-lg" />
  <Canvas class="h-full w-full flex items-center justify-center" />
</div>

</template>

<script lang="ts" setup>
import Canvas from "./canvas/Canvas.vue";
import ElementsMenu from "./controls/ElementsMenu.vue";

</script>