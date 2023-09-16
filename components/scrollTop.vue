<template>
  <button
    id="scrollToTopButton"
    class="group fixed w-10 h-10 bg-orange-600 rounded-full justify-center items-center text-center hover:bg-orange-300 bottom-16 right-28 hidden hover:shadow-sm hover:shadow-white"
    @click="scrollToTop"
  >
    <svg
      xmlns="http://www.w3.org/2000/svg"
      fill="none"
      viewBox="0 0 24 24"
      stroke-width="1.5"
      stroke="currentColor"
      class="group-hover:text-black w-6 h-6 text-white animate-bounce"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        d="M4.5 12.75l7.5-7.5 7.5 7.5m-15 6l7.5-7.5 7.5 7.5"
      />
    </svg>
  </button>
</template>

<script>
export default {
  mounted() {
    window.addEventListener('scroll', this.toggleScrollButton)
  },
  methods: {
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth',
      })
    },

    toggleScrollButton() {
      const scrollToTopButton = document.getElementById('scrollToTopButton')
      if (scrollToTopButton) {
        if (window.scrollY >= 70) {
          scrollToTopButton.style.display = 'flex'
        } else {
          scrollToTopButton.style.display = 'none'
        }
      }
    },
  },
}
</script>
