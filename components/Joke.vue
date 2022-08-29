<template>
  <div class="joke">
    {{ joke }}
  </div>
</template>

<script>
export default {
    name: 'Joke',
    props: ['joke', 'id']
}
</script>

<style>
    .joke {
        padding: 1rem;
        margin: 1rem 0;
        border: 1px dotted #ccc;
    }
</style>