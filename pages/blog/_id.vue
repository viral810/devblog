<template>
  <section class="container">
    <Header />
    <article>
      <h1>{{title}}</h1>
      <p>{{body}}</p>
      <nuxt-link :to="'/'">Back</nuxt-link>
    </article>
  </section>
</template>

<script>
import Header from '~/components/Header.vue'
import axios from 'axios'

export default {
  components: {
    Header
  },
  validate ({ params }) {
    return !isNaN(+params.id)
  },
  async asyncData({params, error}){
    const {data} = await axios.get(`https://jsonplaceholder.typicode.com/posts/${+params.id}`)
    return data
  }
}
</script>

<style>
.container {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
}
</style>

