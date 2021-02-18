<template>
  <div>
      <Search v-on:search-text="searchText" />
      <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
  </div>
</template>

<script>
import axios from "axios";
import Joke from "../../components/Joke"
import Search from "../../components/Search"

export default {
    components: {
        Joke,
        Search
    },
    data() {
        return {
            jokes: []
        }
    },
    async created(){
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }
    try {
        const res = await axios.get('https://icanhazdadjoke.com/search', config);

        this.jokes = res.data.results;
    } catch (err) {
        console.log(err)
    }
    },
    methods: {
        async searchText(text) {
             const config = {
            headers: {
                'Accept': 'application/json'
            }
        };
             try {
        const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);

        this.jokes = res.data.results;
    } catch (err) {
        console.log(err)
    }
        }
    },
head() {
        return {
            title: 'Dad Jokes as far as the eye can see',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'List of a whole lotta Dad Jokes'
                }
            ]
        }
    }
}
</script>

<style>
</style>
