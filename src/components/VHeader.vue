<template>
  <header class="header">
    <RouterLink to="/">
      <img class="header__logo" src="@/assets/img/logo.png" alt="Логотип" />
    </RouterLink>
    <h1 class="header__title">Otus "JS Professional" project</h1>
  </header>
</template>
<script setup></script>
<style lang="sass" scoped>
@import "@/assets/styles/variables"
.header
  display: flex
  align-items: center
  justify-content: center
  padding: 40px
  &__logo
    max-height: 40px
    margin-right: 40px
  &__title
    font-weight: 700
    font-size: 40px
    position: relative
    &::after
      content: ''
      display: block
      position: absolute
      bottom: -4px
      left: 0
      width: 100%
      height: 2px
      background-color: $accent-color
      border-radius: 4px
</style>
