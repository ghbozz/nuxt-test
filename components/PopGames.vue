<template>
  <section class="section is-medium">
    <div class="container-fluid">
      <div class="features-background">
        <h1 class="title">Popular Games</h1>
        <div class="columns is-mobile is-multiline is-vcentered">
          <div v-for="(game, i) in games" :key="i" class="column"><app-game-card :game="game"></app-game-card></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import GameCard from '@/components/GameCard.vue'
export default {
  props: ['games'],
  components: {
    appGameCard: GameCard
  }
}
</script>

<style scoped>
  .container-fluid {
    background-color: rgb(248, 250, 252);
    margin: 0 auto;
    padding: 50px;
    border-radius: 10px;
  }

  .column {
    display: flex;
    justify-content: center;
  }

  .title {
    margin-left: 10px;
    margin-bottom: 100px;
    text-transform: uppercase;
    letter-spacing: .2rem;
  }
</style>
