<template>
  <button
      class="btn"
      :class="color"
      @click.prevent="$emit('action')"
  >
    <slot>{{ text }}</slot>
  </button>
</template>

<script>
export default {
  emits: [
    'action',
  ],
  props: {
    text: {
      type: String,
      default: 'Button',
    },
    color: {
      type: String,
      default: '',
    }
  }
}
</script>

<style scoped>

</style>