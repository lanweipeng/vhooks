<template>
  <div ref="elementRef" style="padding: 16px; background: #fff;">
    <div
      style="width: 300px; height: 180px; background: rgba(0,1,0,0.1); margin-bottom: 10px;"
    />
    <button @click="toggleFull()">点击</button>
    <span> isFullscreen: {{ isFullscreen }}</span>
  </div>
</template>

<script lang="ts">
import { useFullscreen } from '@dewfall/vhooks-vue2';
import { ref } from '@vue/composition-api';

export default {
  setup() {
    const elementRef = ref(null);
    const { isFullscreen, toggleFull } = useFullscreen(elementRef);

    return {
      isFullscreen,
      toggleFull,
      elementRef,
    };
  },
};
</script>
