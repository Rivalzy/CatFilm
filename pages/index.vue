<template>
  <div class="">
    <headerCon />
    <div class="bg-slate-950 min-h-screen">
      <caroSel class="h-[100vh]" />
      <footerCon />
    </div>
  </div>
</template>

<script>
import headerCon from '@/components/headerCon.vue'
import caroSel from '@/components/caroSel.vue'
import footerCon from '@/components/footerCon.vue'

export default {
  components: {
    headerCon,
    caroSel,
    footerCon,
  },
  setup() {},
}
</script>
