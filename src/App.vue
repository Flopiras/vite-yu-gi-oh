<script>
import AppMain from './components/AppMain.vue';
import SearchForm from './components/SearchForm.vue';
import axios from 'axios';
import { store } from '../src/data/store';

const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';

const typesEndpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1';

export default {
  components: { AppMain, SearchForm },
  data() {
    return {
      types: [],
    }
  },
  methods: {
    getPokemons(endpoint) {
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

    getTypes(endpoint) {

      axios.get(endpoint).then(res => {
        this.types = res.data;
      })
    },

    fetchFilterType(option) {
      if (option === '--') {
        return this.getPokemons(endpoint)
      }
      const filterEndpoint = `${endpoint}?eq[type1]=${option}`;
      this.getPokemons(filterEndpoint)
    }
  },
  created() {
    this.getPokemons(endpoint);
    this.getTypes(typesEndpoint)
  },
}

</script>

<template>
  <div class="container">
    <header>
      <h1 class="text-center my-4 text-success">Pokémon</h1>
      <SearchForm :options="types" @changeOption="fetchFilterType" />
    </header>
    <main>
      <AppMain />
    </main>
  </div>
</template>

<style lang="scss">
@use './assets/Scss/style.scss'
</style>