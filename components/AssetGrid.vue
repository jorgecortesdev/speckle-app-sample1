<template>
  <div class="grid grid-cols-3 grid-rows-3 h-screen max-w-6xl">
    <template v-for="(asset, index) of assets" :key="asset.id">
      <slot v-bind="{ asset, index }" />
    </template>
  </div>
</template>

<script setup>
const props = defineProps({
  assets: Array
});
</script>
