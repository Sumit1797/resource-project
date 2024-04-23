<template>
  <the-header :title="title">

  </the-header>
  <stored-resource
    :resources="storedresources">
  </stored-resource>
</template>

<script>
import StoredResource from './components/StoredResource.vue'
import TheHeader from './components/TheHeader.vue'

export default {
  name: 'App',
  components: {
    StoredResource,
    TheHeader
  },
  data () {
    return {
      storedresources: [
        {
          id: 'offciial-1', 
          title: 'this is an initial title',
          description: 'a short description',
          link: 'https://vuejs.org'
        },
        {
          id: 'offciial-2', 
          title: 'this is an initial title',
          description: 'a short description for 2nd course',
          link: 'https://google.com'
        }
            ],
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
