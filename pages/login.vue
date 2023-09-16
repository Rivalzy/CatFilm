<template>
  <div>
    <div class="absolute w-full">
      <img
        src="@/assets/img/kamera.jpg"
        class="bg-fixed bg-center bg-cover brightness-50 blur-sm h-screen w-full"
      />
    </div>
    <div class="relative flex justify-center items-center text-center h-screen">
      <div class="w-96 h-96 bg-white rounded-md">
        <router-link to="/" class="flex justify-normal p-5 hover:text-orange-600 duration-150 ease-in-out"
          ><svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-6 h-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M9 15L3 9m0 0l6-6M3 9h12a6 6 0 010 12h-3"
            />
          </svg>
        </router-link>
        <h1 class="font-semibold text-xl">Login</h1>
        <form class="my-5 mx-5">
          <h1 class="text-start">Email</h1>
          <input
            id="email"
            type="text"
            name="email"
            class="w-full h-10 border-2 border-solid border-black p-4 mb-5"
            placeholder="Masukkan Email"
          />
          <h1 class="text-start">Password</h1>
          <input
            id="pass"
            type="password"
            name="pass"
            class="w-full h-10 border-2 border-solid border-black p-4"
            placeholder="Masukkan Password"
          />
        </form>
        <div class="flex justify-center">
          <span
            class="group w-20 h-10 bg-orange-600 rounded-full flex justify-center items-center text-center hover:bg-orange-300 hover:shadow-md hover:shadow-slate-400 duration-150 ease-in-out"
          >
            <router-link to="/admin">
              <h1 class="text-white group-hover:text-black group-hover:font-semibold" >Masuk</h1>
            </router-link>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>
