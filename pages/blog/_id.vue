<template>
  <section class="container">
    <Header />
    <article>
      <h1>{{title.rendered}}</h1>
      <div v-html="content.rendered"></div>
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
    try {
      const {data} = await axios.get(`https://api.viralpatel.blog/wp-json/wp/v2/posts/${+params.id}`)
      return data
    } catch (e) {
      error({ statusCode: 404, message: 'Post not found' })
    }
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

