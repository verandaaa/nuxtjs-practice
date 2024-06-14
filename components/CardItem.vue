<script setup lang="ts">
import type { Card } from "@/model/card";

interface Props {
  card: Card;
  number: number;
}
const { card, number } = defineProps<Props>();
</script>

<template>
  <NuxtLink :to="{ name: 'index-detail-number', params: { number } }">
    <div class="card">
      <div class="thumbnail">
        <div class="image-container">
          <NuxtImg :src="card.image" />
        </div>
        <span>99:99</span>
        <button type="button">
          <span>+</span>
          <span>담기</span>
        </button>
      </div>
      <p class="description">{{ card.description }}</p>
      <p class="title">{{ card.title }}</p>
      <div class="count-container">
        <p class="view-count">조회수 {{ card.viewCount }}</p>
        <p class="like-count">좋아요 {{ card.likeCount }}</p>
      </div>
    </div>
  </NuxtLink>
</template>

<style scoped>
a {
  text-decoration: none;
}

.card {
  width: 100%;
  border: 1px solid rgb(0, 0, 0, 0.1);
  font-size: 13px;
  font-family: "Nanum Gothic", sans-serif;
}

.thumbnail {
  position: relative;
}

.thumbnail::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: black;
  opacity: 0;
}

.thumbnail:hover::before {
  opacity: 0.5;
}

.thumbnail:hover > span {
  display: none;
}

.thumbnail:hover > button {
  display: inline-block;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.image-container {
  width: 100%;
  aspect-ratio: 194/109;
  background-color: gray;
}

.image-container > img {
  width: 100%;
  display: block;
}

.thumbnail > span,
button {
  position: absolute;
  right: 5px;
  bottom: 5px;
  padding: 0 7px;
  background-color: black;
  font-size: 11px;
  color: #fff;
  font-family: Arial, Helvetica, sans-serif;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.thumbnail > span {
  height: 16px;
}

.thumbnail > button {
  display: none;
  height: 40px;
  cursor: pointer;
}

.description {
  color: #3c3c3c;
  margin-top: 13px;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
  line-height: 15px;
  height: 30px;
}

.title {
  color: #7ba7df;
  margin-top: 8px;
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
  line-height: 15px;
  height: 15px;
}

.count-container {
  margin-top: 10px;
  display: flex;
  gap: 4px;
}

.like-count,
.view-count {
  color: #3c3c3c;
}
</style>
