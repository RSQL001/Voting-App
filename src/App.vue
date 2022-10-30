<script setup>
import NavBar from './components/NavBar.vue'
import WallPaper from './components/WallPaper.vue'
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <NavBar />
  <WallPaper backdrop="Nigeria Decides! 2022" />
  <header>
    <img alt="Vue logo" class="logo" src="./assets/ballot.png" width="125" height="125" />
    <div class="wrapper">
      <HelloWorld msg="Time to Cast Your Ballot" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
  display: flex;
  align-items: end;
  place-content: center;
  padding: 2em 5em 3em 3em;
}

main {
  display: flex;
  align-items: center;
  justify-content: center;
  align-content: space-around;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

}
</style>
