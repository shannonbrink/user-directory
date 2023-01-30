<template>
  <div class="is-flex is-flex-direction-column is-align-items-center px-6">
    <h1 class="title">
      Welcome to the <span class="blue">User Directory</span>!
    </h1>

    <p class="container pb-4">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi viverra enim dolor.
      Etiam vitae eros risus. Nulla condimentum fringilla pharetra. Sed sagittis libero
      eu dolor mollis tincidunt. Vivamus imperdiet fermentum arcu, vel mollis sapien 
      rhoncus et. Maecenas pulvinar quis eros in bibendum. Donec accumsan, est non pulvinar
      scelerisque, sapien tortor malesuada libero, rhoncus eleifend tellus massa sed urna.
      Donec viverra posuere ipsum, vitae congue nulla aliquet sed.
    </p>

    <RouterLink class="btn" to="/users">Browse Users</RouterLink>
  </div>
</template>

<style scoped lang="scss">
.blue {
  color: $matisse;
}
</style>
