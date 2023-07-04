<script>
export default {
    data() {
        return {

        }
    },
    props: {
        options: Array
    }
}
</script>

<template>
    <div class="container">

        <form>
            <select class="form-select my-4">
                <option selected>Select</option>
                <option v-for="option in options">{{ option }}</option>
            </select>
        </form>
    </div>
</template>