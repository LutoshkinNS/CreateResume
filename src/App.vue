<template v-cloak>

  <div class="container column">
    <app-type-blocks @add-block="addBlock"></app-type-blocks>
    <app-view-resume :blocks="blocks"></app-view-resume>
  </div>

  <div class="container">
    <p>
      <app-button
          @action="loadComments"
          color="primary"
      >Загрузить комментарии</app-button>
    </p>
    <app-comments
        :comments="comments"
        v-if="comments.length"
    ></app-comments>
    <app-loader v-if="active"></app-loader>
  </div>

</template>

<script>
import AppTypeBlocks from "./components/AppTypeBlocks";
import AppComments from "./components/AppComments";
import AppButton from "./components/AppButton";
import AppViewResume from "./components/AppViewResume";
import AppLoader from "./components/AppLoader";


export default {
  data() {
    return {
      blocks: [],
      comments: [],
      active: false,
    }
  },
  methods: {
    async loadComments() {
      this.active = true
      const response = await fetch('https://jsonplaceholder.typicode.com/comments?_limit=42')
      this.comments = await response.json()
      this.active = false
    },
    addBlock(block) {
      this.blocks.push(block)
    },
  },
  components: {
    AppTypeBlocks,
    AppComments,
    AppButton,
    AppViewResume,
    AppLoader
  }
}
</script>

<style>

</style>
