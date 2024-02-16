<template>
  <div class="w-screen h-screen bg-blue-950">
    <h1 class="absolute text-7xl font-medium text-blue-500" v-if="!pending">
      {{  asset?.name }}
    </h1>

    <div class="w-full h-full flex items-center justify-center">
      <NuxtLink class="font-bold hover:underline -rotate-90 text-white" to="/">
        Back to gallery
      </NuxtLink>

      <div class="h-2/3 w-1/3 bg-blue-900 rounded-md active" ref="container" />

      <div class="flex flex-col px-2">
        <Transition
          enter-active-class="transition ease-in-out duration-500 transform"
          enter-class="opacity-0 scale-95"
          enter-to-class="opacity-100 scale-100"
        >
          <div class="w-56" v-if="!pending">
            <template v-for="key in Object.keys(asset)" :key="asset[key]">
              <p class="text-white font-bold">
                {{ key }}: <span class="font-light">{{ asset[key] }}</span>
              </p>
            </template>
          </div>
        </Transition>
      </div>
    </div>
  </div>
</template>

<script setup>
const container = ref(null);
const pending = ref(false);

const asset = {
  id: "1",
  name: "Asset Name",
  description: "Asset Description",
  project_id: "1",
  speckle_id: "1",
}
</script>
