<template>
  <h1>Hello World</h1>
    <ul>
        <resource-item v-for="res in storedresources" 
        :key="res.id"
        :title="res.title"
        :description="res.description"
        :link="res.link"></resource-item>
    </ul>
</template>

<script>
import ResourceItem from './components/ResourceItem.vue'

export default {
  name: 'App',
  components: {
    ResourceItem
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
            ]
        }
    }
}
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
