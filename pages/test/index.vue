<template lang='pug'>
  section.hero.is-fullheight
    .hero-body
      .container
        h1.title
          | Fullheight title
        h2.subtitle
          | Fullheight subtitle
        h1
          | test
        button.button.is-primary(@click="showModal()")
          span modal open
    Modal(:title="title" v-model="isShow") 
</template>

<script lang="ts">
import Modal from '../../components/Modal.vue'

export default {
  data() {
    return {
      isShow: false,
      title: 'テストタイトル'
    }
  },
  components: {
    Modal
  },
  methods: {
    showModal() {
      this.isShow = true;
    },
    closeModal() {
      this.isShow = false;
    }
  }
}
</script>

<style>
</style>
