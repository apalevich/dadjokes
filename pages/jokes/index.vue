<template>
  <div>jokes</div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            jokes: []
        }
    },
    async created() {
        const config = {
            headers: {
                Accept: 'application/json'
            }
        };

        try {
            const res = await axios.get('https://icanhazdadjoke.com/search', config)

            this.jokes = res.data.results;
        } catch (e) {
            alert('Sorry we have a problem fetching jokes from the API')
            console.error(e);
        }
    },
    head() {
        return {
            title: 'Dad Jokes',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Best place for corny dad jokes',
                }
            ]
        }
    }
}
</script>

<style>

</style>