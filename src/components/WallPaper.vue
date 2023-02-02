<script setup>
defineProps({
    backdrop:  {
        type: String
    }
})
</script>


<template>
    <img src="/src/assets/flag.webp" class="overlay" alt="..." />
    <div class="banner">
        <h1 class="flyer">{{ backdrop }}</h1>
    </div>

</template>
  
<style scoped>
.overlay {
    position: fixed;
    background-size: contain;
    width: 100%;
    z-index: 0;
    opacity:25%;
}

.banner {
    margin: 0em 0em;
    text-align: center;
}
</style>