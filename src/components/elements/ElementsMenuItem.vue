<template>
  <button
    class="w-10 h-10 border border-zinc-600 rounded flex flex-row items-center justify-center cursor-move"
    draggable="true"
    @dragstart="onDragStart"
  >
    <slot />
  </button>
</template>

<script lang="ts" setup>
function onDragStart(event: DragEvent) {
  // Set data to transfer
  event.dataTransfer?.setData('text/plain', 'button-element');
}
</script>
