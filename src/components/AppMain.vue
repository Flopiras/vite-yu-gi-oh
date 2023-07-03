<script>
import { store } from '../../src/data/store';
import CharacterCard from './CharacterCard.vue';

export default {
    components: { CharacterCard },

    data() {
        return { store }
    }
}
</script>

<template>
    <div class="row row-cols-2 row-cols-md-4 row-cols-lg-6">
        <div class="col" v-for="pokemon in store.pokemons" :key="pokemon.id">
            <CharacterCard :number="pokemon.number" :name="pokemon.name" :type="pokemon.type1" :url="pokemon.imageUrl" />
        </div>
    </div>
</template>

<style lang="scss" scoped></style>