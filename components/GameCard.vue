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
    width: 650px;
    height: 400px;
    border-radius: 10px;
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
</style>
