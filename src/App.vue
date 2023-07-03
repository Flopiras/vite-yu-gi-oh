<script>
import AppMain from './components/AppMain.vue';
export default {
  components: { AppMain },

}
</script>

<template>
  <header>
    <h1 class="text-center my-3 text-success">Pokémon</h1>
  </header>
  <main>
    <AppMain />
  </main>
</template>

<style lang="scss">
@use './assets/Scss/style.scss'
</style>