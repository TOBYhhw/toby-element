<template>
  <button
    ref="_ref"
    class="tb-button"
    :class="{
      [`tb-button--${type}`]: type,
      [`tb-button--${size}`]: size,
      'is-plain': plain,
      'is-round': round,
      'is-circle': circle,
      'is-disabled': disabled,
    }"
    :disabled="disabled"
    :autofocus="autofocus"
    :type="nativeType"
  >
    <span>
      <slot />
    </span>
  </button>
</template>

<script setup lang="ts">
import { ref } from "vue";
import type { ButtonProps } from "./types";
defineOptions({
  name: "TbButton",
});
withDefaults(defineProps<ButtonProps>(), {
  nativeType: "button",
});

const _ref = ref<HTMLButtonElement>();
defineExpose({
  ref: _ref,
});
</script>

<style scoped></style>
