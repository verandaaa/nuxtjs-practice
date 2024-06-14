<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>

<script setup lang="ts"></script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nanum+Gothic&display=swap");

* {
  margin: 0;
  padding: 0;
}

html {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

body {
  border: 1px solid black;
  width: 80%;
  max-width: 1200px;
}

@media screen and (max-width: 640px) {
  body {
    width: 100%;
  }
}
</style>
