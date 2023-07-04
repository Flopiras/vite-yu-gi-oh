<script>
import AppMain from './components/AppMain.vue';
import SearchForm from './components/SearchForm.vue';
import axios from 'axios';
import { store } from '../src/data/store';

const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';

export default {
  components: { AppMain, SearchForm },
  created() {
    store.isLoading = true;
    axios.get(endpoint)
      .then(res => {
        store.pokemons = res.data.docs;
      })
      .catch(() => {
        console.error('error')
      })
      .then(() => {
        store.isLoading = false
      })
  },
}

</script>

<template>
  <div class="container">
    <header>
      <h1 class="text-center my-4 text-success">Pokémon</h1>
      <SearchForm />
    </header>
    <main>
      <AppMain />
    </main>
  </div>
</template>

<style lang="scss">
@use './assets/Scss/style.scss'
</style>