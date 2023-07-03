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
        <img :src="url" :alt="name">
    </div>
</template>

<style lang="scss" scoped></style>