<template>
  <main class="main">
    <VHeader />
    <VNav />
    <div class="content">
      <Transition name="fade">
        <RouterView />
      </Transition>
    </div>
    <footer class="footer"></footer>
  </main>
</template>

<script setup>
import VHeader from "@/components/VHeader.vue";
import VNav from "@/components/VNav.vue";
</script>

<style lang="sass" scoped>
.fade-enter-active,
.fade-leave-active
  transition: opacity 0.5s ease

.fade-enter-from,
.fade-leave-to
  opacity: 0
</style>
