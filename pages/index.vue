<template>
  <div>
    <app-banner></app-banner>
    <app-features></app-features>
  </div>
</template>

<script>
import Banner from '@/components/Banner.vue'
import Plans from '@/components/Plans.vue'
export default {
  components: {
    appBanner: Banner,
    appFeatures: Plans
  }
}
</script>

<style>

</style>
