<template>
  <div
    class="bg-slate-950 sticky top-0 z-[1000] w-full"
    :class="{
      'border-b-[1px] border-solid border-white': borderVisible,
      'bg-transparent': bgVisible,
      'backdrop-blur-sm': bgBlur,
      'font-semibold': textSemiBold,
    }"
  >
    <div class="flex flex-col sm:flex-row">
      <div
        class="flex items-center text-center justify-between px-4 py-4 sm:py-0"
      >
        <div class="border-r-2 border-solid border-white">
          <router-link
            to="/"
            class="uppercase font-semibold text-white text-2xl mr-4"
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
            v-for="item in menu"
            :key="item.title"
            :to="item.link"
            class="block text-white hover:text-orange-600 py-3 sm:py-5 px-4"
            >{{ item.title }}</router-link
          >
        </div>

        <div class="flex flex-col sm:flex-row">
          <div
            class="group flex flex-col sm:flex-row items-center text-center mx-4 text-white gap-1 p-2 bg-orange-500 rounded-lg cursor-pointer hover:bg-orange-300 hover:shadow-md hover:shadow-orange-200 duration-150 ease-in-out"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6 group-hover:text-black"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M15.75 6a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0zM4.501 20.118a7.5 7.5 0 0114.998 0A17.933 17.933 0 0112 21.75c-2.676 0-5.216-.584-7.499-1.632z"
              />
            </svg>
            <router-link to="./login" class="group-hover:text-black">
              <h1>Admin</h1>
            </router-link>
          </div>
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
      borderVisible: false,
      bgVisible: false,
      bgBlur: false,
      textSemiBold: false,
      // Menu
      menu: [
        {
          title: 'Home',
          link: './',
        },
        {
          title: 'All',
          link: './allFilm',
        },
      ],
    }
  },

  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },

  methods: {
    handleScroll() {
      const scrollY = window.scrollY
      if (scrollY >= 50) {
        this.borderVisible = true
        this.bgVisible = true
        this.bgBlur = true
        this.textSemiBold = true
      } else {
        this.borderVisible = false
        this.bgVisible = false
        this.bgBlur = false
        this.textSemiBold = false
      }
    },

    toggle() {
      const Menu = document.getElementById('menu')
      if (Menu.style.display === 'none' || Menu.style.display === '') {
        Menu.style.display = 'flex'
      } else {
        Menu.style.display = 'none'
      }
      this.isMenuOpen = !this.isMenuOpen

      this.hideLoading()
    },
  },
}
</script>
