<template>
  <div class="banner">
    <div class="banner-left">
      <div class="left-content">
        <h1 class="title">This is my title</h1>
        <h3 class="subtitle">Build your next Vue.js application with confidence using NuxtJS.</h3>
      </div>
    </div>
    <div class="banner-right">

    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
  .banner {
    display: flex;
    width: 100vw;
    height: 100vh;
  }

  .banner-left {
    height: 100%;
    width: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    -webkit-box-shadow: inset 0px 0px 10px 0px rgba(0,0,0,0.2);
    -moz-box-shadow: inset 0px 0px 10px 0px rgba(0,0,0,0.2);
    box-shadow: inset 0px 0px 10px 0px rgba(0,0,0,0.2);
  }

  .left-content {
    width: 100%;
    padding: 0% 15%;
  }

  .title {
    font-size: 2.5em;
    text-transform: uppercase;
    letter-spacing: 1rem;
    margin-bottom: 40px;
  }

  .subtitle {
    text-transform: uppercase;
    letter-spacing: .3rem;
  }

  .banner-right {
    background: linear-gradient(42deg, rgba(255,90,90,1) 0%, rgba(255,104,104,1) 100%);
    height: 100%;
    width: 50%;
  }
</style>
