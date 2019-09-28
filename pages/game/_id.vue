<template>
  <div class="container-fluid">
    <div class="game-banner" :style="{ backgroundImage: 'linear-gradient(42deg, rgba(29,29,29,0.2) 0%, rgba(55,55,55,0.3) 100%), url(' + game[0].screenshots[0].url.replace('t_thumb', 't_screenshot_huge') + ')' }">

    </div>
    <h1>this is the game id: {{$route.params.id}} view</h1>
    <!-- {{ game[0].screenshots }} -->
  </div>
</template>

<script>
  import axios from 'axios'

  export default {
    asyncData ({ params, error }) {
      // const proxyurl = 'https://cors-anywhere.herokuapp.com/'
      return axios({
        url: `https://api-v3.igdb.com/games/${params.id}/?fields=name%2Ccover.url%2Csummary%2Cplatforms.name%2Cfirst_release_date%2Cwebsites%2Ctotal_rating%2Cscreenshots.url%2Ctotal_rating&expand=platforms%2Cscreenshots%2Ccover`,
        method: "GET",
        headers: {
            "Accept": "application/json",
            "user-key": 'fa1dc1dd2cfc92ea7689a829c8c15124'
        }
      })
        .then(response => {
          return {
            game: response.data
          }
        })
        .catch(err => {
            console.error(err);
        });
    },
  }
</script>

<style scoped>
  .container-fluid {
    transform: translateY(52px);
  }

  .game-banner {
    height: 500px;
    width: 100vw;
    background-size: cover;
    background-position: top;
  }
</style>

