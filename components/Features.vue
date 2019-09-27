<template>
  <section class="section is-medium">
    <div class="container-fluid">
      <div class="features-background">
        <div class="columns is-mobile is-multiline">
          <div v-for="i in 3" :key="i" class="column"><app-card></app-card></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Card from '@/components/Card.vue'
export default {
  components: {
    appCard: Card
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
</style>
