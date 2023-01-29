<script setup>
import { ref } from 'vue';

let isBurgerOpen = ref(false)
</script>

<template>
  <header class="navbar p-2">
    <div class="navbar-brand">
      <RouterLink to="/">
        <img class="navbar-item" src="@/assets/logo.svg" alt="user directory logo" />
      </RouterLink>

      <a
        class="navbar-burger"
        role="button"
        aria-label="menu"
        aria-expanded="false"
        data-target="headerNavbar"
        @click="isBurgerOpen = !isBurgerOpen"
      >
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>
    
    <div class="navbar-start is-hidden-touch">
      <p class="navbar-item">User Directory</p>
    </div>

    <div
      id="headerNavbar"
      class="navbar-menu"
      :class="{ 'is-active': isBurgerOpen }"
    >
      <nav class="navbar-end">
        <RouterLink class="navbar-item" to="/">
          Home
        </RouterLink>
        <RouterLink class="navbar-item" to="/users">
          Users
        </RouterLink>
      </nav>
    </div>
  </header>
</template>

<style scoped lang="scss">

</style>
