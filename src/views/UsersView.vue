<script setup>
import { ref, onMounted } from 'vue';
import UsersExport from '../components/users/UsersExport.vue'
import UsersCard from '../components/users/UsersCard.vue'
import UsersPagination from '../components/users/UsersPagination.vue'
import axios from 'axios'

let users = ref([])
let pageNumber = ref(1)

function getNextPage() {
  pageNumber.value += 1

  if (pageNumber.value == 0) pageNumber.value = 1
  
  getUsers();
}

function getPreviousPage() {
  pageNumber.value -= 1

  if (pageNumber.value == 0) pageNumber.value = 1
  
  getUsers();
}

async function getUsers() {
  await axios
    .get(`https://randomuser.me/api/?page=${pageNumber.value}&results=10&seed=shannonbrink`)
    .then(response => {
      users.value = response.data.results

      console.log(users.value)
    })
}

onMounted(() => {
  getUsers()
})
</script>

<template>
  <main>
    <UsersExport :page-number="pageNumber" />

    <UsersCard :users="users"/>

    <UsersPagination
      :page-number="pageNumber"
      @next-page="getNextPage"
      @previous-page="getPreviousPage"
    />
  </main>
</template>
