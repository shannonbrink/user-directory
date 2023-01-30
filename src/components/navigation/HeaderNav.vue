<script setup>
import { ref } from 'vue'

let isBurgerOpen = ref(false)
</script>

<template>
  <header class="header navbar is-transparent">
    <div class="navbar-brand" :class="{ 'navbar-bottom-border': isBurgerOpen }">
      <RouterLink to="/">
        <figure class="image is-96x96">
          <img class="logo" src="@/assets/logo.svg" alt="user directory logo" />
        </figure>
      </RouterLink>

      <a
        class="navbar-burger"
        role="button"
        aria-label="menu"
        aria-expanded="false"
        data-target="headerNavbar"
        :class="{ 'is-active': isBurgerOpen }"
        @click="isBurgerOpen = !isBurgerOpen"
      >
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div
      id="headerNavbar"
      class="navbar-menu"
      :class="{ 'is-active': isBurgerOpen }"
    >
      <nav class="navbar-end">
        <RouterLink
          class="navbar-item"
          to="/"
          @click="isBurgerOpen = !isBurgerOpen"
        >
          Home
        </RouterLink>
        <RouterLink
          class="navbar-item"
          to="/users"
          @click="isBurgerOpen = !isBurgerOpen"
        >
          Users
        </RouterLink>
      </nav>
    </div>
  </header>
</template>

<style scoped lang="scss">
.navbar {
  padding: 3rem 4rem;
  background-color: $outer-space;
}

.navbar-burger {
  height: unset;
  color: $alabaster;

  &:hover {
    background-color: transparent;
  }

  span {
    width: 1.5rem;
  }
}

.navbar-item {
  font-size: 1.2rem;
  font-weight: 700;
  color: $alabaster;

  &:hover,
  &:active,
  &:focus {
    color: $picton-blue;
    background-color: transparent;
  }
}

.navbar-menu {
  background-color: transparent;
  box-shadow: none;
}

@media screen and (max-width: 1023px) {
  .navbar {
    padding: 1rem;
  }

  .navbar-bottom-border {
    padding-bottom: 1rem;
    border-bottom: 1px solid $alabaster;
  }
}

@media screen and (max-width: 768px) {
  .navbar-item {
    font-size: 1rem;
  }
}
</style>
