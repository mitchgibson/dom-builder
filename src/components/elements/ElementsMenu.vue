<template>
  <div class="flex flex-row gap-x-1.5">
    <ElementsMenuItem :type="ElementType.Row">
      <RowIcon />
    </ElementsMenuItem>
    <ElementsMenuItem :type="ElementType.Column">
      <ColumnIcon />
    </ElementsMenuItem>
    <ElementsMenuItem :type="ElementType.Button">
      <ButtonIcon />
    </ElementsMenuItem>
    <ElementsMenuItem :type="ElementType.Text">
      <TextIcon />
    </ElementsMenuItem>
    <ElementsMenuItem :type="ElementType.Image">
      <ImageIcon />
    </ElementsMenuItem>
  </div>
</template>

<script lang="ts" setup>
import { ElementType } from "@/domain/element/Element";
import ElementsMenuItem from "./ElementsMenuItem.vue";
import ButtonIcon from "./button/ButtonIcon.vue";
import TextIcon from "./text/TextIcon.vue";
import ImageIcon from "./image/ImageIcon.vue";
import RowIcon from "./row/RowIcon.vue";
import ColumnIcon from "./column/ColumnIcon.vue";
</script>
