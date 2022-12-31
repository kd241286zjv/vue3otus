<template>
  <div class="homepage">
    <h2 class="homepage__title">General info</h2>
    <div class="homepage__block">
      <h3 class="homepage__header">Course name:</h3>
      <p class="homepage__textblock">JavaScript Developer. Professional</p>
    </div>
    <div class="homepage__block">
      <h3 class="homepage__header">Days past:</h3>
      <p class="homepage__textblock">{{ daysPast }}</p>
    </div>
    <div class="homepage__block">
      <h3 class="homepage__header">Homeworks done:</h3>
      <p class="homepage__textblock">{{ homeworksCount }}</p>
    </div>
    <div class="homepage__block">
      <h3 class="homepage__header">Homeworks total:</h3>
      <p class="homepage__textblock">41</p>
    </div>
    <div class="homepage__block">
      <h3 class="homepage__header">Homeworks progress:</h3>
      <div
        class="homepage__progressbar progressbar"
        :data-progress="Math.round((100 / 41) * 1) + '%'"
      >
        <div class="progressbar__completed" :style="{ width: progress }"></div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { lessons } from "@/enums/lessons";
import { computed } from "vue";

const startDate = new Date("2022-09-29");
const currentDate = new Date();
const daysPast = computed(() =>
  Math.floor((+currentDate - +startDate) / 3600000 / 24)
);
const homeworksCount = computed(
  () => lessons.filter((lesson) => lesson.homework).length
);
const progress = Math.round((100 / 41) * 1) + "%";
</script>

<style lang="sass" scoped>
@import '@/assets/styles/_variables.sass'

.homepage
  padding: 40px
  &__title
    font-weight: 500
    font-size: 40px
    margin-bottom: 60px
  &__header
    font-weight: 500
    font-size: 28px
    margin-bottom: 28px
  &__textblock
    font-size: 18px
    font-weight: 400
    color: $secondary-color
  &__block
    margin-bottom: 40px
  .progressbar
    width: 100%
    height: 36px
    padding: 10px
    position: relative
    text-align: center
    background-color: $background-color
    &::before
      content: attr(data-progress)
      display: flex
      align-items: center
      justify-content: center
      text-align: center
      width: 100%
      height: 100%
      position: absolute
      top: 0
      left: 0
      font-weight: 600
      font-size: 24px
    &__completed
      position: absolute
      width: calc(100% - 4px)
      height: calc(100% - 4px)
      top: 2px
      left: 2px
      background-color: $accent-color
</style>
