<template>

<div class="h-full w-full relative bg-zinc-900 text-zinc-400">
  <ElementsMenu class="absolute bottom-5 left-1/2 -translate-x-1/2" />
  <AttributesPanel class="absolute top-1/2 -translate-y-1/2 left-5 h-[70%] border border-zinc-600 rounded-lg" />
  <ToolsMenu class="absolute top-5 left-1/2 -translate-x-1/2 min-w-96 h-12 border border-zinc-600 rounded-lg" />
  <Canvas class="h-full w-full flex items-center justify-center" />
</div>

</template>

<script lang="ts" setup>
import Canvas from "./canvas/Canvas.vue";
import ElementsMenu from "./elements/ElementsMenu.vue";
import AttributesPanel from "./controls/AttributesPanel.vue";
import ToolsMenu from "./controls/ToolsMenu.vue";

</script>