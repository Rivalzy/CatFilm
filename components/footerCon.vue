<template>
  <footer class="bg-slate-950 border-t-[1px] border-slate-300">
    <div class="p-3 flex sm:flex-row flex-col justify-around gap-2 sm:gap-4">
      <div class="sm:w-96 w-[200px]">
        <h1 class="text-white uppercase text-[12px] sm:text-2xl font-semibold">
          Film<span class="text-orange-600">apik</span>
        </h1>
        <p
          class="text-white text-[10px] sm:text-[15px] whitespace-normal sm:w-96 w-[200px]"
        >
          Filmapik adalah platform daring yang menyediakan informasi terkini
          tentang film-film yang sedang tren. Pengguna dapat menemukan ulasan,
          sinopsis, dan berita terbaru seputar dunia perfilman.
        </p>
      </div>

      <div class="w-80">
        <a
          class="sm:text-2xl text-[12px] font-semi bold text-center text-white hover:text-orange-400 hover:border-b-2 duration-200 ease-in-out uppercase cursor-pointer"
        >
          Contact
        </a>

        <!-- Contact -->
        <ul class="text-white flex flex-col justify-start py-2 px-4">
          <!-- instgram -->
          <li class="flex flex-row text-center items-center">
            <svg
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="w-4 h-4 sm:w-6 sm:h-6 text-orange-600"
            >
              <rect x="2" y="2" width="20" height="20" rx="5" ry="5" />
              <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z" />
              <line x1="17.5" y1="6.5" x2="17.51" y2="6.5" />
            </svg>
            <h2 class="text-white ml-2 text-[10px] sm:text-[15px]">
              @FilmApik_
            </h2>
          </li>

          <!-- email -->
          <li class="flex flex-row text-center items-center">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-4 h-4 sm:w-6 sm:h-6 text-orange-600"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"
              />
            </svg>
            <a
              href=""
              class="text-white ml-2 text-[10px] sm:text-[15px] hover:text-orange-600"
              >Film4pik@gmail.com</a
            >
          </li>
        </ul>
      </div>
    </div>
    <div
      class="text-white bg-slate-900 w-full text-center p-1 text-[11px] sm:text-[13px]"
    >
      <p>Copyright © 2023 - All right reserved by FILMAPIK Industries</p>
    </div>
  </footer>
</template>
