<template>
  <section class="section is-medium">
    <div class="container-fluid">
      <div class="features-background">
        <div class="columns is-mobile is-multiline is-vcentered">
          <div v-for="(plan, i) in plans" :key="i" class="column"><app-card :plan="plan"></app-card></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Card from '@/components/Card.vue'
export default {
  data () {
    return {
      plans: [
        { name: 'silver', price: 7.5 },
        { name: 'gold', price: 12.5 },
        { name: 'diamond', price: 15 }
      ]
    }
  },
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

  .columns :nth-child(2) .my-card {
    width: 380px;
    height: 530px;
  }
</style>
