<script setup>
import { RouterView } from 'vue-router'
import HeaderNav from './components/navigation/HeaderNav.vue'
import FooterNav from './components/navigation/FooterNav.vue'
</script>

<template>
  <div id="app">
    <HeaderNav />

    <RouterView class="hero is-halfheight py-6"/>

    <FooterNav />
  </div>
</template>

<style lang="scss">
#app {
  font-family: 'Helvetica', sans-serif;
  background-color: $alabaster;
  color: $outer-space;
}

.btn {
  background-color: $matisse;
  color: $alabaster;
  font-size: 1rem;
  font-weight: 700;
  padding: 1rem;
  border: none;
  border-radius: 5px;
  cursor: pointer;

  &:hover,
  &:active,
  &:focus {
    background-color: $picton-blue;
    color: $alabaster;
  }

  &:disabled {
    background-color: $geyser;
    color: $gull-gray;
    cursor: default;
  }
}
</style>
