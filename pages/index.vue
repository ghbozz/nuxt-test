<template>
  <div>
    <app-banner></app-banner>
    <app-features></app-features>
  </div>
</template>

<script>
import Banner from '@/components/Banner.vue'
import Features from '@/components/Features.vue'
export default {
  components: {
    appBanner: Banner,
    appFeatures: Features
  }
}
</script>

<style>

</style>
