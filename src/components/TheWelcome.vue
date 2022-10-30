<script setup>
import WelcomeItem from './WelcomeItem.vue'
import { ref } from 'vue'

const countA = ref(0)
const countB = ref(0)
const countC = ref(0)
</script>

<template>
  <WelcomeItem>
    <div class="card" style="width: 18rem;">
      <img src="../assets/peter.jpg" class="card-img-top" alt="...">
      <div class="card-body">
        <div class="inner-left">
          <h1 class="card-title">{{ countA }}</h1>
          <p class="card-title">votes</p>
        </div>

        <div class="inner-right">
          <h4 class="card-title">Peter Obi</h4>
          <h6 class="card-title">Labour Party</h6>
        </div>
      </div>

      <a href="#" v-on:click.once="countA++" class="btn btn-primary">Vote</a>
    </div>
  </WelcomeItem>

  <WelcomeItem>
    <div class="card" style="width: 18rem;">
      <img src="../assets/tinubu.png" class="card-img-top" alt="...">
      <div class="card-body">
        <div class="inner-left">
          <h1 class="card-title">{{ countB }}</h1>
          <p class="card-title">votes</p>
        </div>

        <div class="inner-right">
          <h4 class="card-title">Bola Tinubu</h4>
          <h6 class="card-title">All Progressive Congress</h6>
        </div>
      </div>
      <a href="#" v-on:click.once="countB++" class="btn btn-primary">Vote</a>
    </div>
  </WelcomeItem>

  <WelcomeItem>
    <div class="card" style="width: 18rem;">
      <img src="../assets/atiku.png" class="card-img-top" alt="...">
      <div class="card-body">
        <div class="inner-left">
          <h1 class="card-title">{{ countC }}</h1>
          <p class="card-title">votes</p>
        </div>

        <div class="inner-right">
          <h4 class="card-title">Atiku Abubakar</h4>
          <h6 class="card-title">People's Democratic Party</h6>
        </div>
      </div>
      <a href="#" v-on:click.once="countC++" class="btn btn-primary">Vote</a>
    </div>
  </WelcomeItem>

</template>

<style>
.card-body {
  padding: 2em 0.2em;
  align-items: center;
  display: flex;
  font-family: 'Source Sans Pro';
  font-size: 10px;
  justify-content: space-evenly;

}

.inner-left {
  padding-right: 5em;
  text-align: center;
}


.inner-right {}

h1.card-title {
  margin: -0.2em;
}

h1.flyer {
  color: white;
  font-size: 6em;
  font-weight: 600;
}

h3.card-title {
  font-size: 2.3em;
  margin: -5px 0px -5px 0px;
}

h4.card-title {
  margin: 0em;
  font-weight: 600;
  font-size: 2.5em;
}


h5.card-title {
  margin: 5px 0px -3px 0px;
}

p.card-text {
  font-weight: 00;
  margin-left: 5px;
}

p.card-title {
  font-weight: 600;
  font-size: 16px;
  margin-bottom: 0em;
}
</style>