<template>
  <the-header :title="title">

  </the-header>
  <the-resource>
  </the-resource>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import TheResource from './components/TheResource.vue'

export default {
  name: 'App',
  components: {
    TheHeader,
    TheResource
  },
  data () {
    return {
        title:"Just header"
        }
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
