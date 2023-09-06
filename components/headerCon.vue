<template>
  <div class="bg-slate-950 sticky top-0 z-[1000] w-full">
    <div class="flex flex-col sm:flex-row">
      <div
        class="flex items-center text-center justify-between px-4 py-4 sm:py-0"
      >
        <div>
          <router-link
            to="/"
            class="uppercase font-semibold text-white text-2xl"
            >film<span class="text-orange-600">apik</span></router-link
          >
        </div>

        <div class="flex justify-end w-full sm:block sm:justify-normal sm:w-0">
          <!-- hamburger menu -->
          <button
            class="focus:outline-none text-white text-center items-center sm:hidden"
            @click="toggle"
          >
            <!-- Open -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6"
              :class="{ hidden: isMenuOpen, block: !isMenuOpen }"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
              />
            </svg>

            <!-- Close -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6"
              :class="{ hidden: !isMenuOpen, block: isMenuOpen }"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </div>

      <div
        id="menu"
        class="hidden sm:flex flex-col sm:flex-row justify-between w-full items-start text-start sm:items-center sm:text-center"
      >
        <div class="flex flex-col sm:flex-row">
          <router-link
            to="/"
            class="block text-white hover:text-orange-600 py-3 sm:py-5 px-4"
            >Home</router-link
          >
          <router-link
            to="/movies"
            class="block text-white hover:text-orange-600 py-3 sm:py-5 px-4"
            >Movies</router-link
          >
          <router-link
            to="series"
            class="block text-white hover:text-orange-600 py-3 sm:py-5 px-4"
            >Series</router-link
          >
          <router-link
            to="anime"
            class="block text-white hover:text-orange-600 py-3 sm:py-5 px-4"
            >Anime</router-link
          >
        </div>
        <!-- search bar -->
        <div class="flex flex-col sm:flex-row">
          <form action="" class="w-max py-3 px-4 sm:py-5">
            <input
              id="search"
              type="text"
              name="search"
              class="relative z-10 bg-transparent w-full h-12 rounded-full border-2 cursor-pointer outline-none pl-12 pr-4 focus:border-orange-300 focus:shadow-orange-300 focus:shadow-md focus:cursor-text border-orange-600 text-white"
              placeholder="Search"
            />
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="absolute inset-y-0 my-auto w-12 h-8 px-3.5 hidden sm:block text-white border-transparent peer-focus:border-orange-600 peer-focus:stroke-orange-300"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z"
              />
            </svg>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false,
    }
  },
  methods: {
    toggle() {
      const menu = document.getElementById('menu')
      if (menu.style.display === 'none' || menu.style.display === '') {
        menu.style.display = 'flex'
      } else {
        menu.style.display = 'none'
      }
      this.isMenuOpen = !this.isMenuOpen
    },
  },
}
</script>
