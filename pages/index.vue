<template>
  <div>
    <headerCon />
    <div class="bg-slate-950 h-screen">
      <caroSel class="h-[90vh]" />
      <div class="bg-slate-950">
        <div class="flex justify-center text-center items-center">
          <div
            class="w-full h-10 mx-[200px] bg-orange-300 rounded-sm flex justify-start items-center text-left"
          >
            <h1 class="px-2 text-xl font-semibold text-white">New</h1>
          </div>
        </div>

        <div class="flex gap-8 px-[200px] py-5">
          <router-link
            v-for="(item, index) in items"
            :key="index"
            :to="item.route"
          >
            <div
              class="group w-40 h-72 bg-white cursor-pointer hover:bg-orange-500 hover:shadow-lg hover:shadow-white hover:scale-[1.10] transition-all duration-[250] ease-in-out"
            >
              <img
                :src="item.imageSrc"
                :alt="item.alt"
                class="w-full h-40 object-cover"
              />
              <div
                class="text-center items-center px-2 text-slate-500 group-hover:text-white"
              >
                <div class="flex justify-center items-center text-center">
                  <div
                    class="w-14 h-6 mt-2 mb-2 bg-orange-500 group-hover:bg-orange-300 rounded-md"
                  >
                    <h2 class="text-[15px] text-white group-hover:text-black">
                      {{ item.category }}
                    </h2>
                  </div>
                </div>
                <h1 class="mb-3">{{ item.title }}</h1>
                <p class="text-sm">{{ item.genre }}</p>
              </div>
            </div>
          </router-link>
        </div>
      </div>
      <scrollTop />
      <footerCon />
    </div>
  </div>
</template>

<script>
import headerCon from '@/components/headerCon.vue'
import caroSel from '@/components/caroSel.vue'
import footerCon from '@/components/footerCon.vue'
import scrollTop from '~/components/scrollTop.vue'

export default {
  components: {
    headerCon,
    caroSel,
    footerCon,
    scrollTop,
  },

  data() {
    return {
      items: [
        {
          route: '#',
          imageSrc:
            'https://static1.colliderimages.com/wordpress/wp-content/uploads/2023/02/guardians-of-the-galaxy-vol-3-movie-poster.jpg',
          category: 'Movies',
          title: 'Guardian Of Galaxy Vol 3',
          genre: 'Action',
          alt: 'gof',
        },
        {
          route: '#',
          imageSrc:
            'https://en-images.kinorium.com/movie/1080/2005077.jpg?1671813806',
          category: 'Movies',
          title: 'Spiderman Across the Spider Verse',
          genre: 'Action',
          alt: 'spider',
        },
      ],
    }
  },
}
</script>
