<template>
  <section class="container">
    <Header />
  </section>
</template>

<script>
import Header from '~/components/Header.vue'

export default {
  components: {
    Header
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

