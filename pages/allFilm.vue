<template>
  <div>
    <headerCon />
    <div class="bg-slate-950 h-screen">
      <div class="px-28 py-8">
        <div
          class="w-full h-14 bg-orange-300 flex justify-between text-center items-center rounded-lg px-5"
        >
          <h1 class="text-2xl text-white font-semibold">All</h1>

          <!-- search bar -->
          <div class="flex flex-row items-center text-center relative">
            <input
              id="search"
              v-model="searchQuery"
              type="text"
              name="search"
              class="bg-transparent w-full h-12 rounded-l-full border-2 cursor-pointer outline-none pl-5 pr-11 focus:border-orange-600 focus:shadow-orange-600 focus:shadow-md focus:cursor-text border-orange-600 text-white"
              placeholder="Search"
            />
            <select
              v-model="selectedFilter"
              class="absolute top-0 right-5 w-2  h-full bg-transparent text-black cursor-pointer outline-none pl-4 pr-2 focus:border-orange-600"
            >
              <option value="All">All</option>
              <option value="Movies">Movies</option>
              <option value="Animasi">Animasi</option>
            </select>
          </div>
          <!-- search bar end -->
        </div>
      </div>
      <div class="flex gap-8 px-28">
        <cardItem v-for="(card, i) in resultQuery" :key="i" :card="card" />
      </div>
    </div>
    <footerCon />
  </div>
</template>

<script>
import cardItem from '~/components/Card/cardItem.vue'
export default {
  components: {
    cardItem,
  },

  data() {
    return {
      searchQuery: '',
      selectedFilter: 'All',

      cards: [
        {
          route: '#',
          catalog: 'Movies',
          imgSrc:
            'https://static1.colliderimages.com/wordpress/wp-content/uploads/2023/02/guardians-of-the-galaxy-vol-3-movie-poster.jpg',
          rate: '8.5',
          title: 'Guardian Of Galaxy Vol 3',
          genre: 'Action',
        },
        {
          route: '#',
          catalog: 'Animasi',
          imgSrc:
            'https://en-images.kinorium.com/movie/1080/2005077.jpg?1671813806',
          rate: '9.0',
          title: 'Spiderman Across the Spider Verse',
          genre: 'Adventure',
        },
      ],
    }
  },

  computed: {
    resultQuery() {
      if (this.searchQuery) {
        return this.cards.filter((item) => {
          const searchWords = this.searchQuery.toLowerCase().split(' ')
          return (
            (this.selectedFilter === 'All' ||
              item.catalog.toLowerCase() ===
                this.selectedFilter.toLowerCase()) &&
            searchWords.some((searchWord) => {
              return (
                item.title.toLowerCase().includes(searchWord) ||
                item.catalog.toLowerCase().includes(searchWord) ||
                item.genre.toLowerCase().includes(searchWord)
              )
            })
          )
        })
      } else if (this.selectedFilter === 'All') {
        return this.cards
      } else {
        return this.cards.filter(
          (item) =>
            item.catalog.toLowerCase() === this.selectedFilter.toLowerCase()
        )
      }
    },
  },
}
</script>
