<template>
  <section class="container mx-auto py-4 px-4 lg:px-10 xl:px-20 flex flex-col md:flex-row items-center">
    <!-- title content (mobile) -->
    <div class="md:text-left mb-4 pr-4 flex md:hidden">
      <h1 class="text-4xl font-bold text-green">
        Good Food Us Good Mood
      </h1>
    </div>

    <!-- right content -->
    <div class="w-full flex justify-center md:w-1/2 lg:w-3/5 md:order-2">
      <img src="/icons/product-desktop.jpg" alt="Salad" class="w-full max-w-md md:max-w-md hidden md:flex" />
      <img src="/icons/product-mobile.jpg" alt="Salad" class="w-full max-w-md md:max-w-md flex md:hidden" />
    </div>

    <!--left content -->
    <div class="flex flex-col justify-center md:text-left mt-4 md:mt-0 md:w-1/2 lg:w-2/5 md:order-1">
      <h1 class="text-4xl lg:text-7xl font-medium text-green mb-5 lg:mb-10 hidden md:flex">
        Good Food Us Good Mood
      </h1>
      <p class="text-gray-500 w-full md:w-xs lg:w-md tracking-wide">
        I would think that conserving our natural resources should be a conservative position: Not to waste food, and not to throw away a lot of the food that we buy.
      </p>
      <div class="mt-6 flex flex-row gap-4">
        <button class="bg-green text-white px-6 py-3 rounded-full shadow-xl">
          Daftar Sekarang
        </button>
        <button class="bg-gray-100 text-gray-700 px-6 py-3 rounded-full shadow-xl">
          About Us
        </button>
      </div>
    </div>
  </section>

  <section class="overflow-hidden">
    <div class="container mx-auto py-4 px-4 lg:px-10 xl:px-20">
      <h1 class="text-3xl font-bold">Browser Our Category</h1>
      <h1 class="text-green text-3xl font-semibold">Receipt</h1>

      <!-- Wrapper Card -->
      <div 
        ref="scrollContainer"
        class="relative mt-10 max-md:overflow-x-auto transition-transform duration-500 ease-in-out"
         :style="{ transform: `translateX(-${translate}px)` }"
      >
        <div class="flex space-x-4 w-max">
          <FoodCarousel
            v-for="(category, index) in visibleCategories"
            :key="category.name + index"
            v-bind="category"
            :bgColor="category.bgColor"
          />
        </div>
      </div>

      <!-- Navigation buttons -->
      <div class="justify-end mt-10 space-x-4 hidden md:flex">
        <button
            @click="prev"
            :disabled="translate === 0"
            class="flex items-center space-x-2 px-4 py-2 bg-green text-white rounded-full cursor-pointer"
          >
          <span class="w-8 h-8 bg-white text-green flex items-center justify-center rounded-full text-xl">
            &lt;
          </span>
          <span>PREV</span>
        </button>
        
        <button
          @click="next"
          :disabled="translate >= maxTranslate"
          class="flex items-center space-x-2 px-4 py-2 bg-green text-white rounded-full cursor-pointer"
        >
          <span>NEXT</span>
          <span class="w-8 h-8 bg-white text-green flex items-center justify-center rounded-full text-xl">
            &gt;
          </span>
        </button>
      </div>
    </div>
  </section>

  <section class="container mx-auto py-4 px-4 lg:px-10 xl:px-20">
    <h1 class="text-3xl font-bold">Browser Our Trending</h1>
    <h1 class="text-green text-3xl font-semibold">Receipt</h1>

    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6 mt-10">
      <FoodCard 
        v-for="(item, index) in foods" 
        :key="index" :food="item"
        :bgColor="item.bgColor"
      />
    </div>
    <div class="flex justify-center mt-10 mb-24">
      <button class="bg-green text-white px-6 py-2 rounded-full">ALL Receipt</button>
    </div>
  </section>
</template>

<script setup lang="ts">
const translate = ref(0);
const cardWidth = 220;
const gap = 16;
const visibleCards = ref(1);

const categories = ref([
  { name: "Cupcake", items: 22, image: "/icons/cupcake-icon.png", bgColor: "bg-light-green" },
  { name: "Pizza", items: 25, image: "/icons/pizza-icon.png", bgColor: "bg-light-blue" },
  { name: "Kebab", items: 12, image: "/icons/kebab-icon.png", bgColor: "bg-light-cyan" },
  { name: "Salmon", items: 22, image: "/icons/salmon-icon.png", bgColor: "bg-light-red" },
  { name: "Doughnut", items: 11, image: "/icons/doughnut-icon.png", bgColor: "bg-light-lime" },
  { name: "Cupcake", items: 22, image: "/icons/cupcake-icon.png", bgColor: "bg-light-green" },
  { name: "Pizza", items: 25, image: "/icons/pizza-icon.png", bgColor: "bg-light-blue" },
]);

const selectedIndex = ref<number>(0);
const visibleCategories = computed(() => {
  return categories.value.slice(selectedIndex.value, selectedIndex.value + 7);
});

const updateVisibleCards = () => {
  const screenWidth = window.innerWidth;
  if (screenWidth >= 1280) {
    visibleCards.value = 3;
  } else if (screenWidth >= 1024) {
    visibleCards.value = 2;
  } else {
    visibleCards.value = 1;
  }
};

onMounted(() => {
  updateVisibleCards();
  window.addEventListener('resize', updateVisibleCards);
});

onUnmounted(() => {
  window.removeEventListener('resize', updateVisibleCards);
});

const maxTranslate = computed(() => {
  const totalWidth = categories.value.length * (cardWidth + gap);
  const visibleWidth = visibleCards.value * (cardWidth + gap);
  return Math.max(0, totalWidth - visibleWidth);
});

const next = () => {
  if (translate.value + (cardWidth + gap) * visibleCards.value <= maxTranslate.value) {
    translate.value += (cardWidth + gap) * visibleCards.value;
  } else {
    translate.value = maxTranslate.value; // Batasi ke maxTranslate
  }
};

const prev = () => {
  if (translate.value - (cardWidth + gap) * visibleCards.value >= 0) {
    translate.value -= (cardWidth + gap) * visibleCards.value;
  } else {
    translate.value = 0;
  }
};

const foods = ref([
  { name: 'Pizza Paperoni', category: 'Pizza', rating: 3, image: '/icons/pizza-paperoni.jpg', bgColor: 'bg-light-blue' },
  { name: 'Pizza Meat', category: 'Pizza', rating: 3, image: '/icons/pizza-meat.jpg', bgColor: 'bg-light-blue' },
  { name: 'Doner Kebab', category: 'Kebab', rating: 5, image: '/icons/doner-kebab.jpg', bgColor: 'bg-light-cyan' },
  { name: 'Salmon Roll', category: 'Salmon', rating: 4, image: '/icons/salmon-roll.jpg', bgColor: 'bg-light-red' },
  { name: 'Cupcake Choco', category: 'Cupcake', rating: 3, image: '/icons/cupcake-choco.jpg', bgColor: 'bg-light-green' },
  { name: 'Doughnut Milk', category: 'Doughnut', rating: 5, image: '/icons/doughnut-milk.jpg', bgColor: 'bg-light-lime' },
  { name: 'Doughnut Unicorn', category: 'Doughnut', rating: 3, image: '/icons/doughnut-unicorn.jpg', bgColor: 'bg-light-lime' },
  { name: 'Kathi Kebab', category: 'Kebab', rating: 4, image: '/icons/kathi-kebab.jpg', bgColor: 'bg-light-cyan' }
]);
</script>