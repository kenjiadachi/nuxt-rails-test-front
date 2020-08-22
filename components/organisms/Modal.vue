<template lang='pug'>
.modal(:class="{ 'is-active': value }")
  .modal-background(@click="closeModal()")
  .modal-card
    header.modal-card-head
      button.delete(aria-label="close" @click="closeModal()")
    section.modal-card-body
      p.title {{ title }}
    footer.modal-card-foot
      button.button(aria-label="close" @click="closeModal()") 閉じる
</template>

<script lang='ts'>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    value: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    closeModal() {
      // @ts-ignore
      this.$emit('input', false)
    }
  }
}
</script>