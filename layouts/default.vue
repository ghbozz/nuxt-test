<template>
  <div>
    <app-nav></app-nav>
    <nuxt />
  </div>
</template>

<script>
import axios from 'axios'
axios.defaults.headers.common['user-key'] = 'fa1dc1dd2cfc92ea7689a829c8c15124'

import Nav from '@/components/Nav.vue'

export default {
  components: {
    appNav: Nav
  }
}
</script>

<style>

</style>
