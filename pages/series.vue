<template>
  <div class="container">
    <headerCon />
    <div class="bg-slate-950 min-h-screen flex justify-center items-center">
      <h1 class="text-white font-semibold text-2xl">Not Found</h1>
    </div>
    <footerCon />
  </div>
</template>

<script>
import headerCon from '@/components/headerCon.vue'
import footerCon from '@/components/footerCon.vue'

export default {
  components: {
    headerCon,
    footerCon
  },
}
</script>