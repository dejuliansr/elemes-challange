<template>
  <header class="container mx-auto py-4 px-4 lg:px-10 xl:px-20 flex justify-between items-center">
    <img src="/icons/logo.png" alt="Logo" class="h-8 lg:h-14 w-auto" />

     <!-- Desktop Navigation -->
     <nav class="hidden lg:flex space-x-10">
      <NuxtLink to="#" class="text-gray-500 hover:text-gray-600 font-medium">Home</NuxtLink>
      <NuxtLink to="#" class="text-gray-500 hover:text-gray-600 font-medium">About</NuxtLink>
      <NuxtLink to="#" class="relative text-gray-500 hover:text-gray-600 font-medium">
        <span class="absolute -top-5 -right-1/2 transform -translate-x-1/2 bg-red-500 text-white text-xs font-bold px-3 py-1 rounded-full">
          Hot
        </span>
        Promotions
      </NuxtLink>
      <NuxtLink to="#" class="text-gray-500 hover:text-gray-600 font-medium">Blogs</NuxtLink>
      <NuxtLink to="#" class="text-gray-500 hover:text-gray-600 font-medium">Contact Us</NuxtLink>
    </nav>

    <!-- Auth Buttons -->
    <div class="flex items-center space-x-4">
      <button class="text-black font-medium cursor-pointer hidden lg:flex">Masuk</button>
      <button class="bg-green text-white px-5 py-2 rounded-full cursor-pointer">
        Daftar Sekarang
      </button>
    </div>
  </header>
  
  <!-- Bottom Navigation (Mobile Only) -->
  <nav class="fixed bottom-0 left-0 right-0 w-full bg-white border-t border-gray-300 container mx-auto py-4 px-4 flex justify-between items-center lg:hidden z-50">
    <NuxtLink to="#" class="flex flex-col items-center text-gray-500">
      <img src="/icons/menu-burger.svg" class="w-10 h-10" alt="Home" />
      <span class="text-xs">Home</span>
    </NuxtLink>
    <NuxtLink to="#" class="flex flex-col items-center text-gray-500">
      <img src="/icons/menu-burger.svg" class="w-10 h-10" alt="Promotions" />
      <span class="text-xs">Promotions</span>
    </NuxtLink>
    <NuxtLink to="#" class="flex flex-col items-center text-gray-500">
      <img src="/icons/menu-burger.svg" class="w-10 h-10" alt="Others" />
      <span class="text-xs">Others</span>
    </NuxtLink>
  </nav>
</template>