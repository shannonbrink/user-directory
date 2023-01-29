<script setup>
import { RouterView } from 'vue-router'
import HeaderNav from './components/navigation/HeaderNav.vue'
import FooterNav from './components/navigation/FooterNav.vue'
</script>

<template>
  <div id="app" class="hero is-fullheight">
    <HeaderNav />

    <RouterView />

    <FooterNav />
  </div>
</template>

<style lang="scss">
#app {
  font-family: 'Helvetica', sans-serif;
}
</style>
