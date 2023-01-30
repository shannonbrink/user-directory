<script setup>
const props = defineProps({
  users: Array
})
</script>

<template>
  <div class="users columns is-centered">
    <div class="column tile is-parent is-vertical is-three-fifths-desktop">
      <div
        class="users-card columns tile is-child"
        v-for="user in users"
        :key="user.id.value"
      >
        <div class="column is-narrow has-text-centered-mobile py-0">
          <img
            class="users-image"
            :src="user.picture.large"
            :alt="`image of ${user.name.first} ${user.name.last}`"
          />
        </div>

        <ul class="users-info column">
          <li class="capitalize is-size-5 has-text-weight-bold has-text-centered-mobile">
            {{ user.name.first }} {{ user.name.last }}
          </li>
          <li class="capitalize">
            Age: {{ user.dob.age }}
          </li>
          <li class="capitalize">
            Gender: {{ user.gender }}
          </li>
          <li>
            Email: {{ user.email }}
          </li>
          <li>
            Phone: {{ user.phone }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.users {
  &-card {
    background-color: $alabaster;
    border: 1px solid $geyser;
    padding: 1.5rem 1rem;
    box-shadow: .5rem .5rem .5rem $geyser;
  }

  &-image {
    border: 5px solid $picton-blue;
    border-radius: 100%;
  }

  &-info li {
    padding: .5rem 0;

    &:not(:last-child) {
      border-bottom: 1px solid $geyser;
    }
  }
}
</style>
