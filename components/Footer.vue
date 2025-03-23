<template>
    <footer class="py-28">
      <div class="container mx-auto bg-light-green p-6 lg:px-20 grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-8">
        <!-- Logo dan Alamat -->
        <div>
          <div class="flex items-center space-x-2">
            <img src="/icons/logo.png" alt="Logo" class="h-10" />
          </div>
          <p class="mt-4 text-gray-500 text-sm leading-relaxed">
            Jl. Prof. DR. Satrio No.7, RT.3/RW.3, Karet Kuningan, Kecamatan Setiabudi, Kota Jakarta Selatan, 
            Daerah Khusus Ibukota Jakarta 12950
          </p>
          <!-- Icon Sosial -->
          <div class="flex space-x-3 mt-4">
            <!-- Email Icon -->
            <div class="group flex items-center justify-center w-10 h-10 rounded-full bg-white hover:bg-green cursor-pointer transition duration-300">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" 
                class="w-6 h-6 text-green group-hover:text-white fill-current">
                <path d="M22 6c0-1.1-.9-2-2-2H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2zm-2 0l-8 5l-8-5zm0 12H4V8l8 5l8-5z"/>
              </svg>
            </div>

            <!-- Phone Icon -->
            <div class="group flex items-center justify-center w-10 h-10 rounded-full bg-white hover:bg-green cursor-pointer transition duration-300">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" 
                class="w-6 h-6 text-green group-hover:text-white fill-current">
                <path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 4h4l2 5l-2.5 1.5a11 11 0 0 0 5 5L15 13l5 2v4a2 2 0 0 1-2 2A16 16 0 0 1 3 6a2 2 0 0 1 2-2"/>
              </svg>
            </div>

            <!-- Instagram Icon -->
            <div class="group flex items-center justify-center w-10 h-10 rounded-full bg-white hover:bg-green cursor-pointer transition duration-300">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" 
                class="w-6 h-6 text-green group-hover:text-white fill-current">
                <path d="M7 2C4.79 2 3 3.79 3 6v12c0 2.21 1.79 4 4 4h10c2.21 0 4-1.79 4-4V6c0-2.21-1.79-4-4-4H7m0 2h10c1.11 0 2 .89 2 2v12c0 1.11-.89 2-2 2H7c-1.11 0-2-.89-2-2V6c0-1.11.89-2 2-2m5 2c-3.31 0-6 2.69-6 6s2.69 6 6 6 6-2.69 6-6-2.69-6-6-6m0 2a4 4 0 0 1 4 4 4 4 0 0 1-4 4 4 4 0 0 1-4-4 4 4 0 0 1 4-4m5-2c-.55 0-1 .45-1 1s.45 1 1 1 1-.45 1-1-.45-1-1-1z"/>
              </svg>
            </div>
          </div>
        </div>

        <!-- Categories -->
        <div>
          <h3 class="font-semibold text-gray-800">Categories</h3>
          <ul class="mt-4 space-y-2 text-gray-500">
            <li>
              <NuxtLink to="#">Cupcake</NuxtLink>
            </li>
            <li>
              <NuxtLink to="#">Pizza</NuxtLink>
            </li>
            <li>
              <NuxtLink to="#">Kebab</NuxtLink>
            </li>
            <li>
              <NuxtLink to="#">Salmon</NuxtLink>
            </li>
            <li>
              <NuxtLink to="#">Doughnut</NuxtLink>
            </li>
          </ul>
        </div>

        <!-- About Us -->
        <div>
          <h3 class="font-semibold text-gray-800">About Us</h3>
          <ul class="mt-4 space-y-2 text-gray-500">
            <li>
              <NuxtLink to="#">About Us</NuxtLink>
            </li>
            <li>
              <NuxtLink to="#">Faq</NuxtLink>
            </li>
            <li>
              <NuxtLink to="#">Report Problem</NuxtLink>
            </li>
          </ul>
        </div>

        <!-- Newsletter -->
        <div>
          <h3 class="font-semibold text-gray-800">Newsletter</h3>
          <p class="mt-4 text-gray-500 text-sm">
            Get now free 50% discount for all products on your first order
          </p>
          <div class="flex mt-4">
            <input 
              type="email" 
              placeholder="Your email address" 
              class="border border-gray-300 p-2 w-full rounded-l-md text-gray-600 focus:outline-none"
            />
            <button class="bg-green text-white px-4 rounded-r-md">SEND</button>
          </div>
          <div class="mt-4 space-y-2 font-medium">
            <div class="flex items-center space-x-2">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" 
                class="w-6 h-6 text-green group-hover:text-white fill-current">
                <path d="M22 6c0-1.1-.9-2-2-2H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2zm-2 0l-8 5l-8-5zm0 12H4V8l8 5l8-5z"/>
              </svg>
              <span>elemesid@gmail.com</span>
            </div>
            <div class="flex items-center space-x-2">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" 
                class="w-6 h-6 text-green group-hover:text-white fill-current">
                <path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 4h4l2 5l-2.5 1.5a11 11 0 0 0 5 5L15 13l5 2v4a2 2 0 0 1-2 2A16 16 0 0 1 3 6a2 2 0 0 1 2-2"/>
              </svg>
              <span>0888 1111 2222</span>
            </div>
          </div>
        </div>
      </div>
      <!-- Copyright -->
      <div class="text-center text-gray-500 text-sm mt-10">
        © 2021 ELEMES ID. ALL RIGHTS RESERVED
      </div>
  </footer>
</template>