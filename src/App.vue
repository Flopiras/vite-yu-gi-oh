<script>
import AppMain from './components/AppMain.vue';
import axios from 'axios';

export default {
  components: { AppMain },

}
</script>

<template>
  <div class="container">
    <header>
      <h1 class="text-center my-3 text-success">Pokémon</h1>
    </header>
    <main>
      <AppMain />
    </main>
  </div>
</template>

<style lang="scss">
@use './assets/Scss/style.scss'
</style>