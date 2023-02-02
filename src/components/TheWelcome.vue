<script setup>
import WelcomeItem from './WelcomeItem.vue'
import { ref } from 'vue'
import { computed } from '@vue/reactivity';
import { onMounted } from 'vue';

</script>

<script>
export default {
  data() {
    return {
      candidate1: 0,
      candidate2: 0,
      candidate3: 0,
      pressed: false,
    };
  },


  mounted() {
    //No. 3 
    this.setCandidate();
  },


   methods: {
    //No 4 Reads data saved into candidate values from the memory card
    setCandidate() {
      let savedCandidate1 = localStorage.getItem("candidate1");
      if (savedCandidate1) this.candidate1 = Number(savedCandidate1);

      let savedCandidate2 = localStorage.getItem("candidate2");
      if (savedCandidate2) this.candidate2 = Number(savedCandidate2);

      let savedCandidate3 = localStorage.getItem("candidate3");
      if (savedCandidate3) this.candidate3 = Number(savedCandidate3);
    },

    warnUser() {
      alert('You are part of the problem of this country. How many times do you want to vote for your favorite candidate');
    },

    //No. 2 Assign the functionality of the button based off the inherent value of the button
    handleClick(value) {

      switch (value) {

        case 'candidate1':
          this.candidate1++;
          localStorage.setItem("candidate1", this.candidate1);
          break;

        case 'candidate2':
          this.candidate2++;
          localStorage.setItem("candidate2", this.candidate2);
          break;

        case 'candidate3':
          this.candidate3++;
          localStorage.setItem("candidate3", this.candidate3);
          break;
      };
    },
   
    press() {
    this.pressed = true;
    console.log(this.pressed);
  },

  }
}




</script>

<template>
  <WelcomeItem>
    <div class="card" style="width: 18rem;">
      <img src="../assets/peter.jpg" class="card-img-top" alt="...">
      <div class="card-body">
        <div class="inner-left">
          <h1 class="card-title">{{ candidate1 }}</h1>
          <p class="card-title">votes</p>
        </div>

        <div class="inner-right">
          <h4 class="card-title">Peter Obi</h4>
          <h6 class="card-title">Labour Party</h6>
        </div>
      </div>

      <!-- No. 1 Runs the handleClick function on any click event-->
      <a href="#" @click.once="handleClick('candidate1')" class="btn btn-primary">Vote</a>
    </div>
  </WelcomeItem>

  <WelcomeItem>
    <div class="card" style="width: 18rem;">
      <img src="../assets/tinubu.png" class="card-img-top" alt="...">
      <div class="card-body">
        <div class="inner-left">
          <h1 class="card-title">{{ candidate2 }}</h1>
          <p class="card-title">votes</p>
        </div>

        <div class="inner-right">
          <h4 class="card-title">Bola Tinubu</h4>
          <h6 class="card-title">All Progressive Congress</h6>
        </div>
      </div>
      <a href="#" @click.once="handleClick('candidate2')" class="btn btn-primary">Vote</a>
    </div>
  </WelcomeItem>

  <WelcomeItem>
    <div class="card" style="width: 18rem;">
      <img src="../assets/atiku.png" class="card-img-top" alt="...">
      <div class="card-body">
        <div class="inner-left">
          <h1 class="card-title">{{ candidate3 }}</h1>
          <p class="card-title">votes</p>
        </div>

        <div class="inner-right">
          <h4 class="card-title">Atiku Abubakar</h4>
          <h6 class="card-title">People's Democratic Party</h6>
        </div>
      </div>
      <a href="#" @click.once="handleClick('candidate3'), press()" class="btn btn-primary">Vote</a>
      <div v-if="pressed">Presser</div>
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