<script>
export default {
    props: {
        generation: Number,
        position: Number,
        name: String,
        type: String,
        url: String
    }

}
</script>

<template>
    <div class="character-card text-center ">
        <h4 class="pt-2">Generation: {{ generation }}</h4>
        <img class="img-fluid rounded-circle my-3" :src="url" :alt="name">
        <h4># {{ position }}</h4>
        <h3>{{ name }}</h3>
        <h5>{{ type }}</h5>
    </div>
</template>

<style lang="scss" scoped>
.character-card {
    background-color: burlywood;
    border-radius: 30px;
    border: 2px solid orangered;
}

img {
    width: 200px;
    height: 200px;
}
</style>