<template>

<div class="h-full w-full relative bg-zinc-900 text-zinc-400">
  <ElementsMenu class="z-100 absolute bottom-5 left-1/2 -translate-x-1/2 bg-zinc-900" />
  <AttributesPanel class="z-100 absolute top-1/2 -translate-y-1/2 left-5 h-[70%] border border-zinc-600 rounded-lg bg-zinc-900" />
  <ToolsMenu class="z-100 absolute top-5 left-1/2 -translate-x-1/2 min-w-96 h-12 border border-zinc-600 rounded-lg bg-zinc-900" />
  <Canvas class="z-90 h-full w-full flex items-center justify-center" />
</div>

</template>

<script lang="ts" setup>
import Canvas from "./canvas/Canvas.vue";
import ElementsMenu from "./elements/ElementsMenu.vue";
import AttributesPanel from "./controls/AttributesPanel.vue";
import ToolsMenu from "./controls/ToolsMenu.vue";

</script>