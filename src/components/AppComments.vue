<template>
  <div class="card">
    <h2>Комментарии</h2>
    <ul class="list">
      <li class="list-item" v-for="comment in comments" :key="comments.id">
        <div>
          <p><strong>{{ comment.email }}</strong></p>
          <small>{{ comment.name }}</small>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    comments: {
      type: Array
    },
  }
}
</script>

<style scoped>

</style>