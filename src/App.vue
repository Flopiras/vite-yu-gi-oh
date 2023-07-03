<script>
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import { store } from '../src/data/store';

const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';

export default {
  components: { AppMain },
  created() {
    axios.get(endpoint).then(res => {
      store.pokemons = res.data.docs;
    })
  },


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