<template>
  <nav class="menu">
    <RouterLink
      v-for="lesson in lessons"
      :key="lesson.id"
      class="menu__item"
      active-class="menu__item--active"
      :to="`/lessons/${lesson.id}`"
      >{{ lesson.title }}</RouterLink
    >
  </nav>
</template>
<script setup>
import { lessons } from "@/enums/lessons";
</script>
<style lang="sass" scoped>
@import "@/assets/styles/variables"
.menu
  display: flex
  flex-direction: column
  padding: 40px

  &__item
    color: $secondary-color
    text-decoration: none
    margin-bottom: 20px
    transition: color $trns
    position: relative


    &--active
      color: $accent-color

      &::before
        content: ''
        display: block
        width: 10px
        height: 10px
        background-image: url('@/assets/img/arrow-left.svg')
        position: absolute
        top: 4px
        right: -30px

    &:hover
      color: $primary-color
</style>
