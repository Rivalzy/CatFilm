<template>
  <div>
    <slot :current-slide="currentSlide" />

    <!-- Navigasi -->
    <div
      class="pt-0 pb-[16px] h-full w-full absolute flex justify-center items-center"
    >
      <div class="flex flex-1 px-3">
        <i
          class="bg-orange-600 text-white cursor-pointer flex items-center justify-center rounded-[50%] w-10 h-10"
          @click="prevSlide"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-8 h-8 p-1"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M15.75 19.5L8.25 12l7.5-7.5"
            />
          </svg>
        </i>
      </div>
      <div class="flex flex-1 justify-end px-3">
        <i
          class="bg-orange-600 text-white cursor-pointer flex items-center justify-center rounded-[50%] w-10 h-10"
          @click="nextSlide"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-8 h-8 p-1"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M8.25 4.5l7.5 7.5-7.5 7.5"
            />
          </svg>
        </i>
      </div>
    </div>

    <!-- radio -->
    <div
      class="absolute bottom-6 w-full flex gap-4 justify-center items-center"
    >
      <span
        v-for="(slide, index) in getSlideCount"
        :key="index"
        :class="{ active: index + 1 === currentSlide }"
        class="cursor-pointer w-3 h-3 rounded-[50%] bg-white"
        @click="goToSlide(index)"
      >
      </span>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'

export default {
  setup() {
    const currentSlide = ref(1)
    const getSlideCount = ref(null)
    const autoPlay = ref(true)
    const timeDuration = ref(5000)

    // Next Slide
    const nextSlide = () => {
      if (currentSlide.value === getSlideCount.value) {
        currentSlide.value = 1
        return
      }
      currentSlide.value += 1
    }

    // Prev Slide
    const prevSlide = () => {
      if (currentSlide.value === 1) {
        currentSlide.value = getSlideCount.value
        return
      }
      currentSlide.value -= 1
    }

    const goToSlide = (index) => {
      currentSlide.value = index + 1
    }

    // auto play
    const auto = () => {
      setInterval(() => {
        prevSlide()
      }, timeDuration.value)
    }

    if (autoPlay.value) {
      auto()
    }

    onMounted(() => {
      getSlideCount.value = document.querySelectorAll('.slide').length
    })

    return { currentSlide, nextSlide, prevSlide, getSlideCount, goToSlide }
  },
}
</script>

<style>
.active {
  background-color: #FFA500;
}
</style>
