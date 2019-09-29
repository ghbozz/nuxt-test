<template>
  <div class="container-fluid">
    <div class="game-banner" :style="{ backgroundImage: 'linear-gradient(42deg, rgba(29,29,29,0.2) 0%, rgba(55,55,55,0.3) 100%), url(' + game[0].screenshots[0].url.replace('t_thumb', 't_screenshot_huge') + ')' }">

    </div>
    <div class="container details-container">
      <div class="columns">
        <div class="column">
          <img class="card-cover" :src="game[0].cover.url.replace('t_thumb', 't_cover_big')" alt="">
        </div>
        <div class="column is-two-thirds">
          <div class="game-details">
            <h1 class="title">{{ game[0].name }}</h1>
            <span v-for="platform in game[0].platforms">{{ platform.name }} / </span>
            <p class="summary">{{ game[0].summary }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import axios from 'axios'

  export default {
    asyncData ({ params, error }) {
      const proxyurl = 'https://cors-anywhere.herokuapp.com/'
      return axios({
        url: `${proxyurl}https://api-v3.igdb.com/games/${params.id}/?fields=name%2Ccover.url%2Csummary%2Cplatforms.name%2Cfirst_release_date%2Cwebsites%2Ctotal_rating%2Cscreenshots.url%2Ctotal_rating&expand=platforms%2Cscreenshots%2Ccover`,
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
    height: 400px;
    width: 100vw;
    background-size: cover;
    background-position: center;
  }

  .details-container {
    margin-top: 30px;
  }

  .column {
    display: flex;
    justify-content: center;
  }
</style>

