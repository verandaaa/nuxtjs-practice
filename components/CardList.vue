<script setup>
import { cards } from "@/lib/data";
</script>

<template>
  <div id="card-container">
    <CardItem v-for="(card, index) in cards" :key="index" :card="card" :number="index" />
  </div>
</template>

<style scoped>
#card-container {
  padding: 24px;
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-gap: 17px;
}

@media screen and (max-width: 1024px) {
  #card-container {
    grid-template-columns: repeat(4, 1fr);
  }
}

@media screen and (max-width: 640px) {
  #card-container {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media screen and (max-width: 480px) {
  #card-container {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (max-width: 320px) {
  #card-container {
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>
