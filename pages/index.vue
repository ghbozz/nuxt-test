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
    return axios({
      url: `https://api-v3.igdb.com/games/`,
      method: "GET",
      headers: {
          "Accept": "application/json",
          "user-key": 'fa1dc1dd2cfc92ea7689a829c8c15124'
      },
      data: "fields name,first_release_date,hypes,cover.url,screenshots.url,summary; \nwhere hypes > 50 & first_release_date > 1548679293 & first_release_date < 1569674712;"
    })
      .then(response => {
        return {
          games: response.data
        }
      })
      .catch(err => {
          console.error(err);
      });
  },
}
</script>

<style>

</style>
