<template>
  <div class="lesson-page">
    <h2 class="lesson-page__header">{{ pageTitle }}</h2>
  </div>
</template>
<script setup>
import { computed } from "vue";
import { useRoute } from "vue-router";
import { lessons } from "@/enums/lessons";

const route = useRoute();
const pageTitle = computed(
  () => lessons[route.params.id].id + " _" + lessons[route.params.id].title
);
</script>
<style lang="sass" scoped>
.lesson-page
  padding: 40px
  &__header
    font-size: 30px
    font-weight: 500
</style>
