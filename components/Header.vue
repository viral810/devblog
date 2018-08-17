<template>
  <header>
    <nuxt-link to="/"><app-logo /></nuxt-link>
    <Button text="contact me" link="/contact" color="cream" />
  </header>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'
import Button from '~/components/Button.vue'

export default {
  components: {
    AppLogo,
    Button
  }
}
</script>

<style>
header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  background: #fdf9f3;
  border-bottom: 1px solid rgba(0,0,0,0.33);
  box-shadow: 0 2px 4px 0 rgba(0,0,0,0.13);
  padding: 5px 20px;
}
</style>