<script setup lang="ts">
import { cards } from "@/lib/data";
import type { Card } from "@/model/card";

const route = useRoute();
const card: Card = cards[Number(route.params.number)];
</script>

<template>
  <div id="pop-up-container">
    <div id="pop-up-background" />
    <div id="pop-up-content">
      <div id="pop-up-content-sub">
        <p class="title">
          <strong>{{ card.title }}</strong>
        </p>
      </div>
      <div id="pop-up-content-main">
        <div class="image-container">
          <NuxtImg :src="card.image" />
        </div>
        <div class="count-container">
          <p class="view-count">조회수 {{ card.viewCount }}</p>
          <p class="like-count">좋아요 {{ card.likeCount }}</p>
        </div>
        <div class="description-container">
          <p class="description">{{ card.description }}</p>
        </div>
        <NuxtLink to="/" class="button-container">
          <button type="button">닫기</button>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<style scoped>
#pop-up-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}

#pop-up-content {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: white;
  width: 40%;
}

#pop-up-content > * {
  box-sizing: border-box;
  padding: 10px;
}

#pop-up-content-sub {
  height: 10vh;
}

.title {
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
  line-height: 16px;
  height: 16px;
}

#pop-up-content-main {
  display: flex;
  flex-direction: column;
  height: 50vh;
}

.image-container {
  width: 60%;
  aspect-ratio: 194/109;
  background-color: gray;
  margin: auto;
}

.image-container > img {
  width: 100%;
  display: block;
}

.count-container {
  margin-top: 20px;
  display: flex;
  gap: 4px;
  margin-left: auto;
}

.description-container {
  margin-top: 13px;
  flex-grow: 1;
}

.description {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
  line-height: 16px;
  height: 32px;
}

.button-container {
  margin-left: auto;
}

.button-container > button {
  width: 80px;
  height: 30px;
  /* margin-left : auto; */
}
</style>
