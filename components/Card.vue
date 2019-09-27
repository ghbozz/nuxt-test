<template>
  <div class="my-card">
    <div class="top-card">
      <span class="feature-price">{{ plan.price }}€</span>
    </div>
    <div class="bottom-card">
      <h4 class="feature-title title">{{ plan.name }}</h4>
      <p class="feature-desc">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Id nemo nostrum, quasi cumque, tenetur iste porro, minus natus neque, nisi quisquam facere rerum quos architecto.</p>
      <div class="button-box">
        <a href="#" class="btn feature-btn">Buy now</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['plan']
}
</script>

<style scoped>
  .my-card {
    overflow: hidden;
    border-radius: 10px;
    height: 500px;
    width: 350px;
    -webkit-box-shadow: 0px 2px 10px 0px rgba(0,0,0,0.2);
    -moz-box-shadow: 0px 2px 10px 0px rgba(0,0,0,0.2);
    box-shadow: 0px 2px 10px 0px rgba(0,0,0,0.2);
  }

  .top-card {
    height: 40%;
    color: white;
    background: linear-gradient(42deg, rgba(255,90,90,1) 0%, rgba(255,104,104,1) 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 90%);
  }

  .feature-price {
    font-size: 3em;
    font-weight: bolder;
  }

  .feature-title {
    text-transform: uppercase;
  }

  .bottom-card {
    padding: 20px;
    height: 60%;
    position: relative;
  }

  .button-box {
    margin-top: 15px;
    width: 100%;
    text-align: center;
  }

  .btn:link,
  .btn:visited {
    letter-spacing: .2rem;
    display: inline-block;
    width: 200px;
    text-align: center;
    text-transform: uppercase;
    color: white;
    text-decoration: none;
    background: linear-gradient(42deg, rgba(255,90,90,1) 0%, rgba(255,104,104,1) 100%);
    padding: 15px 30px;
    border-radius: 100px;
    font-weight: bolder;
    transition: all .3s ease-out;
  }

  .btn:hover {
    transform: translateY(-5px);
    -webkit-box-shadow: 0px 2px 10px 0px rgba(0,0,0,0.2);
    -moz-box-shadow: 0px 2px 10px 0px rgba(0,0,0,0.2);
    box-shadow: 0px 2px 10px 0px rgba(0,0,0,0.2);
  }

  .btn::after {
    content: '';
    position: absolute;
    z-index: -1;
    top: 0;
    left: 0;
    border-radius: 100px;
    width: 100%;
    height: 100%;
    background: linear-gradient(42deg, rgba(255,90,90,1) 0%, rgba(255,104,104,1) 100%);
    transition: all .3s ease-out;
  }

  .btn:hover::after {
    transform: scaleX(1.2) scaleY(1.5);
    opacity: 0;
  }
</style>
