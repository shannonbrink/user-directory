<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios'
import UsersExport from '../components/users/UsersExport.vue'
import UsersCard from '../components/users/UsersCard.vue'
import UsersPagination from '../components/users/UsersPagination.vue'

let users = ref([])
let pageNumber = ref(1)

async function getNextPage() {
  pageNumber.value += 1

  if (pageNumber.value === 0) pageNumber.value = 1
  
  await getUsers()

  window.scrollTo(0, 0)
}

async function getPreviousPage() {
  pageNumber.value -= 1

  if (pageNumber.value === 0) pageNumber.value = 1
  
  await getUsers()

  window.scrollTo(0, 0)
}

async function getUsers() {
  await axios
    .get(`https://randomuser.me/api/?page=${pageNumber.value}&results=10&seed=shannonbrink`)
    .then(response => {
      users.value = response.data.results
    })
    .catch(error => {
      console.log(error)
    })
}

onMounted(() => {
  getUsers()
})
</script>

<template>
  <main>
    <div class="title-bar is-flex is-justify-content-space-between">
      <h1 class="title is-align-self-center m-0">
        All Users:
      </h1>
      <UsersExport :page-number="pageNumber" />
    </div>

    <UsersCard :users="users" />

    <UsersPagination
      :page-number="pageNumber"
      @next-page="getNextPage"
      @previous-page="getPreviousPage"
    />
  </main>
</template>

<style scoped lang="scss">
.title-bar {
  margin: 0 2rem 2rem;
}

@media screen and (max-width: 768px) {
  .title-bar  {
    margin: 0 1rem 1rem;
  }

  .title {
    font-size: 1.5rem;
  }
}
</style>
