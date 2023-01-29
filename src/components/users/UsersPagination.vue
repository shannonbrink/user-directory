<script setup>
const props = defineProps({
  pageNumber: Number
})
const emit = defineEmits(['change', 'delete'])
const firstPage = 1
</script>

<template>
	<div class="columns is-centered has-text-centered">
		<nav
      class="is-centered"
      role="navigation"
      aria-label="pagination"
    >
			<button
        class="button is-light is-size-6"
        :disabled="pageNumber === firstPage"
        @click="$emit('previousPage')"
      >
				Previous
			</button>

			<button class="button is-light is-size-6" @click="$emit('nextPage')">
				Next page
			</button>
		</nav>
	</div>
</template>

<style scoped lang="scss">

</style>
