<template>
  <div ref="canvasRef" @dragover.prevent @drop="onDrop"></div>
</template>

<script lang="ts" setup>
import type { ElementType } from "@/domain/element/Element";
import { onMounted, onUnmounted, ref, useTemplateRef, watch } from "vue";

const canvasRef = useTemplateRef<HTMLDivElement>("canvasRef");
const canvasObserver = ref<MutationObserver | null>(null);

onMounted(() => {
  if (!canvasRef.value) throw new Error("Canvas ref not found");

  canvasObserver.value = new MutationObserver((mutations) => {
    mutations.forEach((mutation) => {
      console.log("DOM changed:", mutation);
    });
  });

  canvasObserver.value.observe(canvasRef.value, {
    childList: true,
    subtree: true,
    attributes: true,
    characterData: true,
  });
});

onUnmounted(() => {
  canvasObserver.value?.disconnect();
});

function onDrop(event: DragEvent) {
  event.preventDefault();
  const type: ElementType | undefined = event.dataTransfer?.getData("text/plain") as ElementType | undefined;
  if (!type) return;

  if (type === "row") {
    const row = createRow();
    row.style.minHeight = "100px";
    (event.target as HTMLElement)?.appendChild(createWrapper(row, type));
  }
  if (type === "column") {
    const column = createColumn();
    column.style.minHeight = "400px";
    (event.target as HTMLElement)?.appendChild(createWrapper(column, type));
  }
}

function createRow() {
  const row = document.createElement("div");
  row.className = "flex flex-row gap-x-2";
  return row;
}

function createColumn() {
  const column = document.createElement("div");
  column.className = "flex flex-col gap-y-2";
  return column;
}

function createWrapper(element: HTMLElement, type: ElementType) {
  const wrapper = document.createElement("div");
  wrapper.className = "w-full p-2";
  const innerWrapper = document.createElement("div");
  innerWrapper.className = "border border-dashed border-zinc-600 rounded w-full";

  const label = document.createElement("p");
  label.className = "text-xs text-zinc-400 w-full text-center capitalize";
  label.textContent = type;
  wrapper.appendChild(label);
  innerWrapper.appendChild(element);
  wrapper.appendChild(innerWrapper);
  return wrapper;
}
</script>
