<script setup lang="ts">
import { useSlideContext } from '@slidev/client'

const { $page } = useSlideContext()
</script>

<template>
  <div class="slide-number" :aria-label="`Diapositiva ${$page}`">
    {{ $page }}
  </div>
</template>

<style scoped>
.slide-number {
  position: absolute;
  right: 16px;
  bottom: 12px;
  z-index: 1000;
  min-width: 40px;
  padding: 5px 10px;
  border: 1px solid #67e8f9;
  border-radius: 9px;
  background: #164e63;
  color: #fff;
  font-family: sans-serif;
  font-size: 18px;
  font-weight: 700;
  line-height: 1.2;
  text-align: center;
  box-shadow: 0 2px 8px rgb(0 0 0 / 20%);
  pointer-events: none;
}
</style>
