<template>
    <form @submit.prevent="onSubmit">
        <input type="text" v-model="text" placeholder="Find a Joke..." />
        <button type="submit">Search Jokes</button>
    </form>
</template>
<script>
export default {
    name: "SearchJokes",
    data() {
        return {
            text: ''
        }
    },
    methods: {
        onSubmit() {
            this.$emit('search-text', this.text);
            this.text = "";
        }
    }
}
</script>