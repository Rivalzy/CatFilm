<template>
  <div class="flex justify-center pt-10 ">
    <slot :current-slide="currentSlide" />

    <!-- Iamge -->
    <sliderCon v-for="(slide, index) in carouselSlides" :key="index">
      <div v-show="currentSlide === index + 1" class="flex justify-center">
        <img
          :src="require(`@/assets/img/${slide}.jpg`)"
          alt="gambar"
          class="h-[400px] w-[500px] sm:h-[400px] sm:w-[1000px] brightness-[.8] rounded-md object-cover absolute border-2 border-solid border-white"
        />
      </div>
    </sliderCon>

    <!-- Navigasi -->
    <div
      class="pt-0 pb-[16px] h-[400px] w-[500px] sm:h-[400px] sm:w-[1000px] absolute flex justify-center items-center"
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
        <div
          class="absolute bottom-5 w-full flex gap-4 justify-center items-center"
        >
          <span
            v-for="index in getSlideCount"
            :key="index"
            :class="{ active: index + 1 === currentSlide }"
            class="cursor-pointer w-3 h-3 rounded-[50%] bg-white"
            @click="goToSlide(index)"
          >
          </span>
        </div>
      </div>
    </div>

    <!-- radio -->
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'
import sliderCon from '@/components/sliderCon.vue'

export default {
  components: {
    sliderCon,
  },

  setup() {
    const currentSlide = ref(4)
    const getSlideCount = ref(null)
    const autoPlay = ref(true)

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
      }, 3000)
    }

    if (autoPlay.value) {
      auto()
    }

    const carouselSlides = ['spider', 'gof', 'spider', 'gof']

    onMounted(() => {
      getSlideCount.value = document.querySelectorAll('.slide').length
    })

    return {
      currentSlide,
      nextSlide,
      prevSlide,
      getSlideCount,
      goToSlide,
      carouselSlides,
    }
  },
}
</script>

<style>
.active {
  background-color: #ffa500;
}
</style>
