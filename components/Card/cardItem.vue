<template>
  <div>
    <div>
      <router-link :to="card.route">
        <div
          class="group w-40 h-72 bg-white cursor-pointer hover:bg-orange-500 hover:shadow-lg hover:shadow-white hover:scale-[1.10] transition-all duration-[250] ease-in-out"
        >
          <div class="relative">
            <img :src="card.imgSrc" class="w-full h-40 object-cover" />
            <div
              class="absolute top-0 right-0 w-12 h-6 bg-opacity-70 bg-orange-200 rounded-bl-md flex justify-center items-center text-center"
            >
              <div class="flex flex-row items-center gap-1 mx-2">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  height="1em"
                  viewBox="0 0 576 512"
                  class="w-4 h-4 fill-orange-400"
                >
                  <path
                    d="M316.9 18C311.6 7 300.4 0 288.1 0s-23.4 7-28.8 18L195 150.3 51.4 171.5c-12 1.8-22 10.2-25.7 21.7s-.7 24.2 7.9 32.7L137.8 329 113.2 474.7c-2 12 3 24.2 12.9 31.3s23 8 33.8 2.3l128.3-68.5 128.3 68.5c10.8 5.7 23.9 4.9 33.8-2.3s14.9-19.3 12.9-31.3L438.5 329 542.7 225.9c8.6-8.5 11.7-21.2 7.9-32.7s-13.7-19.9-25.7-21.7L381.2 150.3 316.9 18z"
                  />
                </svg>
                <h1 class="text-black text-sm">{{ card.rate }}</h1>
              </div>
            </div>
          </div>
          <div
            class="text-center items-center px-2 text-slate-500 group-hover:text-white"
          >
            <div class="flex justify-center items-center text-center">
              <div
                class="w-14 h-6 mt-2 mb-2 bg-orange-500 group-hover:bg-orange-300 rounded-md"
              >
                <h2 class="text-[15px] text-white group-hover:text-black">
                  {{ card.catalog }}
                </h2>
              </div>
            </div>
            <h1 class="mb-3">{{ card.title }}</h1>
            <p class="text-sm">{{ card.genre }}</p>
          </div>
        </div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    // eslint-disable-next-line vue/require-default-prop
    card: {
      type: Object,
    },
  },
}
</script>
