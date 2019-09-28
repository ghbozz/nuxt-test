<template>
  <div class="game-card" :style="{ backgroundImage: 'linear-gradient(42deg, rgba(29,29,29,0.2) 0%, rgba(55,55,55,0.3) 100%), url(' + game.cover.url.replace('t_thumb', 't_cover_big') + ')' }">
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
    width: 270px;
    height: 370px;
    border-radius: 10px;
  }

  .card-content {
    width: 100%;
    position: absolute;
    transform: translateX(-50%);
    bottom: 30px;
    left: 50%;
    color: white;
    font-size: 24px;
    background-color: rgba(15,15,15,0.5);
  }
</style>
