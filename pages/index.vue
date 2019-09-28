<template>
  <div>
    <app-banner></app-banner>
    <app-features></app-features>
    <app-pop-games :games="games"></app-pop-games>
  </div>
</template>

<script>
import axios from 'axios'

import Banner from '@/components/Banner.vue'
import Plans from '@/components/Plans.vue'
import PopGames from '@/components/PopGames.vue'

export default {
  components: {
    appBanner: Banner,
    appFeatures: Plans,
    appPopGames: PopGames
  },
  asyncData ({ params, error }) {
    return axios.get(`https://api-v3.igdb.com/games/?fields=name,genres.name,cover.url,popularity&order=popularity:desc&expand=genres`)
    .then((res) => {
      return {
        games: res.data.splice(0, 10)
      }
    })
    .catch((e) => {
      console.log(e)
      error({ statusCode: 404, message: 'Billet non trouvé' })
    })
  }
}
</script>

<style>

</style>
