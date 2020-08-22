<template lang='pug'>
  div
    nav-bar
    Message
    .container
      nuxt
</template>

<script lang='ts'>
import NavBar from '../components/organisms/NavBar.vue'
import Message from '../components/organisms/Message.vue'
export default {
  components: {
    NavBar,
    Message
  }
}
</script>