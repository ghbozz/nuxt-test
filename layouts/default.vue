<template>
  <div>
    <app-nav></app-nav>
    <div class="container">
      <nuxt />
    </div>
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
