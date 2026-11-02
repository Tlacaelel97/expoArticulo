<script setup lang="ts">
import cell from '../figuras/cell.png'
import muerteCelular from '../figuras/muerteCelular.png'

defineProps<{ name: 'cell' | 'muerteCelular' }>()
const images = { cell, muerteCelular }
</script>

<template>
  <img :src="images[name]" />
</template>
