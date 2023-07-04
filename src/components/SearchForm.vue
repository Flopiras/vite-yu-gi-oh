<script>
export default {
    data() {
        return {
            selectedOption: ''
        }
    },
    props: {
        options: Array
    },
    emits: ['changeOption']
}
</script>

<template>
    <div class="container">

        <form>
            <select @change="$emit('changeOption', selectedOption)" v-model="selectedOption" class="form-select my-4">
                <option selected>Select</option>
                <option v-for="option in options">{{ option }}</option>
            </select>
        </form>
    </div>
</template>