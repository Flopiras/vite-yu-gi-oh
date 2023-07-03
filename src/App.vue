<script>
import AppMain from './components/AppMain.vue';
import AppLoader from './components/AppLoader.vue';
import axios from 'axios';
import { store } from '../src/data/store';

const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';

export default {
  components: { AppMain, AppLoader },
  created() {
    axios.get(endpoint)
      .then(res => {
        store.isLoading = true;
        store.pokemons = res.data.docs;
      })
      .catch(() => {
        console.error('error')
      })
      .then(() => {
        store.isLoading = false
      })
  },
  data() {
    return { store }
  }
}

</script>

<template>
  <div class="container">
    <AppLoader />
    <header>
      <h1 class="text-center my-4 text-success">Pokémon</h1>
    </header>
    <main>
      <AppMain v-if="!store.isLoading" />
    </main>
  </div>
</template>

<style lang="scss">
@use './assets/Scss/style.scss'
</style>