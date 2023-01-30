<script setup>
const props = defineProps({
  pageNumber: Number
})
const emit = defineEmits(['change', 'delete'])
const firstPage = 1

</script>

<template>
	<div class="is-flex is-justify-content-center">
		<nav
			class="pagination"
			role="navigation"
			aria-label="pagination"
		>
			<button
				class="btn mr-2"
				:disabled="pageNumber === firstPage"
				@click="$emit('previousPage')"
			>
				Prev.
			</button>

			<button class="btn" @click="$emit('nextPage')">
				Next
			</button>
		</nav>
	</div>
</template>

<style scoped lang="scss">
.btn {
	padding: .5rem;
}
</style>
