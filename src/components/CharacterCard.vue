<script>
export default {
    props: {
        number: Number,
        name: String,
        type: String,
        url: String
    }

}
</script>

<template>
    <div class="character-card text-center">
        <img class="img-fluid rounded-circle" :src="url" :alt="name">
        <h3># {{ number }}</h3>
        <h3>{{ name }}</h3>
        <h4>{{ type }}</h4>
    </div>
</template>

<style lang="scss" scoped>
.character-card {
    background-color: burlywood;
}

img {
    width: 200px;
    height: 200px;
}
</style>