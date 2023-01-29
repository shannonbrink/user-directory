<script setup>
const props = defineProps({
  users: Array
})
</script>

<template>
  <div class="columns is-centered">
    <div class="column tile is-parent is-vertical is-three-fifths">
      <div
        class="columns tile is-child box has-text-centered-touch"
        v-for="user in users"
        :key="user.id.value"
      >
        <div class="column is-narrow">
          <img :src="user.picture.large" :alt="`image of ${user.name.first} ${user.name.last}`" />
        </div>

        <div class="column">
          <p class="capitalize">{{ user.name.first }} {{ user.name.last }}</p>
          <p class="capitalize">Age: {{ user.dob.age }}</p>
          <p class="capitalize">Gender: {{ user.gender }}</p>
          <p>Email: {{ user.email }}</p>
          <p>Phone: {{ user.phone }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">

</style>
