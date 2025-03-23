<template>
  <div
    class="p-3 rounded-lg transition-transform duration-300 hover:scale-y-120"
    :class="bgColor"
  >
    <div class="flex flex-col items-center justify-center py-4 px-20">
      <img :src="image" :alt="name" class="w-12 h-12 mb-5" />
      <h4 class="mt-2 font-semibold text-gray-700">
        {{ name }}
      </h4>
      <p class="text-sm text-gray-500">{{ items }} Items</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  name: String,
  items: Number,
  image: String,
  bgColor: String
});
</script>