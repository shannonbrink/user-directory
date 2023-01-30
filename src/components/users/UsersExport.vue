<script setup>
import axios from 'axios'

const props = defineProps({
  pageNumber: Number
})

async function exportToCSV() {
  await axios
    .get(`https://randomuser.me/api/?page=${props.pageNumber}&results=10&seed=shannonbrink&exc=login,nat,cell,registered,location&format=csv&dl`)
    .then((response) => {
      allowDownload(response.data)
    })
    .catch((error) => {
      console.log(error)
    })
}

function allowDownload(data) {
  // create anchor element that is hidden from the page
  const a = document.createElement('a')
  a.style.display = 'none'
  document.body.appendChild(a)

  // anchor element is used for downloading the CSV
  a.href = window.URL.createObjectURL(
    new Blob([data], { type: 'text/csv' })
  )
  a.setAttribute('download', 'users.csv')

  // create click event on the anchor tag to initiate CSV download
  a.click()

  // remove reference to object URL when finished, and cleanup anchor tag from page
  window.URL.revokeObjectURL(a.href)
  document.body.removeChild(a)
}
</script>

<template>
  <button class="btn" @click="exportToCSV">
    Export Page
  </button>
</template>
