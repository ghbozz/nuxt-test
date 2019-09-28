<template>
  <div>
    <app-nav></app-nav>
    <nuxt />
  </div>
</template>

<script>
import Nav from '@/components/Nav.vue'

export default {
  components: {
    appNav: Nav
  }
}
</script>

<style>

</style>
