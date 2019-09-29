<template>
  <div class="game-card" :style="{ backgroundImage: 'linear-gradient(42deg, rgba(29,29,29,0.2) 0%, rgba(55,55,55,0.3) 100%), url(' + game.screenshots[0].url.replace('t_thumb', 't_screenshot_big') + ')' }">
    <img class="card-cover" :src="game.cover.url.replace('t_thumb', 't_cover_big')" alt="">
    <div class="card-content">
      <h1 class="game-title">{{ game.name }}</h1>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['game']
  }
</script>

<style scoped>
  .game-card {
    position: relative;
    background-size: cover;
    background-position: center;
    width: 100%;
    height: 400px;
    border-radius: 10px;
    -webkit-box-shadow: 0px 2px 10px 0px rgba(0,0,0,0.2);
    -moz-box-shadow: 0px 2px 10px 0px rgba(0,0,0,0.2);
    box-shadow: 0px 2px 10px 0px rgba(0,0,0,0.2);
  }

  .card-cover {
    z-index: 1;
    width: 200px;
    height: 300px;
    position: absolute;
    bottom: 5%;
    right: 5%;
    border-radius: 10px;
    border: 2px solid rgba(15,15,15,0.7);
  }

  .card-content {
    width: 100%;
    position: absolute;
    transform: translateX(-50%);
    bottom: 30px;
    left: 50%;
    color: white;
    font-size: 24px;
    background-color: rgba(15,15,15,0.7);
    transition: all .3s ease-out;
  }

  @media screen and (max-width: 767px) {
    .card-cover {
      transform: translate(50%, 50%);
      right: 50%;
      bottom: 50%;
      width: 250px;
      height: 350px;
    }

    .card-content {
      z-index: 2;
    }
  }
</style>
