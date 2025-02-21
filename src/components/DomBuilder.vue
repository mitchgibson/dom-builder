<template>
  <div class="h-full w-full flex flex-col bg-zinc-900 text-zinc-400">
    <div class="h-24 flex flex-row items-center justify-center">
      <ToolsMenu
        class="z-100 min-w-96 h-12 border border-zinc-600 rounded-lg bg-zinc-900"
      />
    </div>
    <div class="flex flex-row grow overflow-hidden">
      <div class="h-full w-48">
        <AttributesPanel
          class="h-[70%] border border-zinc-600 rounded-lg bg-zinc-900"
        />
      </div>
      <div class="flex grow">
        <Canvas class="z-90 h-full w-full min-h-full min-w-full" />
      </div>
      <div class="h-full w-48">
        
      </div>
    </div>
    <div class="h-24 flex flex-row items-center justify-center">
      <ElementsMenu />
    </div>
  </div>
</template>

<script lang="ts" setup>
import Canvas from "./canvas/Canvas.vue";
import ElementsMenu from "./elements/ElementsMenu.vue";
import AttributesPanel from "./controls/AttributesPanel.vue";
import ToolsMenu from "./controls/ToolsMenu.vue";
</script>
