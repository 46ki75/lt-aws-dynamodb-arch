<template>
  <span :class="$style.chip" :style="{ '--color': i ? '#c0cce1' : '#e3e5e8' }">
    <Icon icon="mdi:code" style="display: inline" color="gray" />
    <slot />
  </span>
</template>

<script setup lang="ts">
import { Icon } from "@iconify/vue";

export interface ApiChipProps {
  i?: boolean;
}

withDefaults(defineProps<ApiChipProps>(), {});
</script>

<style module lang="scss">
.chip {
  display: inline-flex;
  gap: 0.25rem;
  justify-content: center;
  align-items: center;
  font-family: monospace;
  padding: 0 0.25rem;
  border-radius: 0.25rem;
  background-color: var(--color);
}
</style>
