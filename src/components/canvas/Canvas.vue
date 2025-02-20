<template>
  <div @dragover.prevent @drop="onDrop">Canvas</div>
</template>

<script lang="ts" setup>
function onDrop(event: DragEvent) {
  event.preventDefault();
  const data = event.dataTransfer?.getData("text/plain");
  console.log("dropped element:", data);
}
</script>
