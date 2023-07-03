<script>
import { store } from '../../src/data/store';

export default {

    data() {
        return { store }
    }
}
</script>

<template>
    <div v-if="store.isLoading" class="overlay">
        <h1>Loading...</h1>
    </div>
</template>

<style lang="scss" scoped>
.overlay {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
}
</style>

