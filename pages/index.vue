<template>
  <div class="">
    <headerCon />
    <div class="bg-slate-950 min-h-screen">
      <caroSel
        v-slot="{ currentSlide }"
        class="relative max-h-[100vh] h-[100vh]"
      >
        <sliderCon v-for="(slide, index) in carouselSlides" :key="index">
          <div
            v-show="currentSlide === index + 1"
            class="w-[100%] top-0 left-0 max-h-full h-full"
          >
            <img
              :src="require(`@/assets/img/${slide}.jpg`)"
              alt=""
              class="min-w-full h-full brightness-[.8] object-cover absolute"
            />
          </div>
        </sliderCon>
      </caroSel>
    </div>
    <footerCon />
  </div>
</template>

<script>
import headerCon from '@/components/headerCon.vue'
import caroSel from '@/components/caroSel.vue'
import sliderCon from '@/components/sliderCon.vue'
import footerCon from '@/components/footerCon.vue'

export default {
  components: {
    headerCon,
    caroSel,
    sliderCon,
    footerCon,
  },
  setup() {
    const carouselSlides = ['spider', 'gof', 'spider', 'gof']

    return { carouselSlides }
  },
}
</script>
