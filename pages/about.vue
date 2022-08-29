<template>
  <div>
    <h1>About the DadJokes</h1>
    <p>This is an app that display corny dad jokes</p>
    <hr>
    <p>
      This page is rendered on the <strong>{{ rendering }}</strong>
    </p>
    <p v-if="rendering === 'server'">
      First load or hard refresh is done on server side.
    </p>
    <p v-if="rendering === 'client'">Navigation is done on client side.</p>
    <ul>
      <li>Refresh the page for server side rendering.</li>
      <li>Click the links to see client side rendering.</li>
    </ul>
    <a href="/about">Links</a>
  </div>
</template>

<script>
export default {
    asyncData() {
        return {
        rendering: process.server ? 'server' : 'client'
        }
    },
    head() {
        return {
            title: 'About the DadJokes',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Best place for corny dad jokes',
                }
            ],
        }
    }
}
</script>

<style>

</style>