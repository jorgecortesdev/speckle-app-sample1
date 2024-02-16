<script setup>
const assets = [
  { id: "1", project_id: "1", speckle_id: "1" },
  { id: "2", project_id: "2", speckle_id: "2" },
  { id: "3", project_id: "3", speckle_id: "3" },
  { id: "4", project_id: "4", speckle_id: "4" },
  { id: "5", project_id: "5", speckle_id: "5" },
  { id: "6", project_id: "6", speckle_id: "6" },
  { id: "7", project_id: "7", speckle_id: "7" },
  { id: "8", project_id: "8", speckle_id: "8" },
  { id: "9", project_id: "9", speckle_id: "9" },
];
</script>

<template>
  <div>
    <h1 class="absolute text-9xl font-medium text-blue-500 z-30 select-none">
      Speckle App Sample
    </h1>

    <AssetPagination>
      <AssetGrid :assets="assets" v-slot="{ asset, index }">
        <NuxtLink :to="`/asset/${asset.id}`">
          <AssetCard
            :class="[
              index % 2 === 1 ? 'bg-blue-900' : 'bg-blue-950',
              'scale-90 hover:scale-95 rounded-md',
            ]"
          />
        </NuxtLink>
      </AssetGrid>
    </AssetPagination>
  </div>
</template>
