<script>
export default {
    data() {
        return {

        }
    }
}
</script>

<template>
    <div class="container">

        <form>
            <select class="form-select my-4">
                <option selected>Select type</option>
                <option v-for="type in types">{{ type }}</option>
            </select>
        </form>
    </div>
</template>