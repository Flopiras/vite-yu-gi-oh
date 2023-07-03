<script>
import { store } from '../../src/data/store';
import AppLoader from './AppLoader.vue';
import CharacterCard from './CharacterCard.vue';

export default {
    components: { CharacterCard, AppLoader },

    data() {
        return { store }
    }
}
</script>

<template>
    <section>
        <AppLoader />

        <div v-if="!store.isLoading" class="row row-cols-2 row-cols-md-4 row-cols-lg-5">
            <div class="col" v-for="pokemon in store.pokemons" :key="pokemon.id">
                <CharacterCard :position="pokemon.number" :name="pokemon.name" :type="pokemon.type1" :url="pokemon.imageUrl"
                    :generation="pokemon.generation" />
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped></style>