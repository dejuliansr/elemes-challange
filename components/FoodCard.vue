// components/FoodCard.vue
<template>
  <div 
    class="rounded-xl p-4 relative transition-all duration-300" 
    :class="bgColor"
  >
    <img 
      :src="food.image" 
      alt="Food Image" 
      class="w-auto h-28 object-cover rounded-lg"
    />
    <h3 class="font-semibold text-2xl mt-3"> {{ food.name }} </h3>
    <p class="text-green font-medium"> {{ food.category }} </p>
    <div class="flex justify-start mt-2">
      <img 
        v-for="n in 5" 
        :key="n" 
        :src="n <= food.rating ? '/icons/star.svg' : '/icons/star-fill.svg'" 
        alt="Star Icon" 
        class="w-5 h-5"
      />
    </div>
  </div>
</template>

<script setup>
defineProps({
  food: Object,
  image: String,
  bgColor: String
});
</script>