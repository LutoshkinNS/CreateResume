<template>
  <form class="card card-w30">
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select id="type" v-model="typeSelect">
        <option value="title">Заголовок</option>
        <option value="subtitle">Подзаголовок</option>
        <option value="avatar">Аватар</option>
        <option value="text">Текст</option>
      </select>
    </div>

    <div class="form-control">
      <label for="value">Значение</label>
      <textarea id="value" rows="3" v-model="value"></textarea>
    </div>

    <app-button
        color="primary"
        @action="addBlock"
        :disabled="value.length < 4"
    >Добавить</app-button>
  </form>
</template>

<script>
import AppButton from "./AppButton";

export default {
  data() {
    return {
      typeSelect: 'title',
      value: ''
    }
  },
  emits: [
    'add-block',
  ],
  methods: {
    addBlock() {
      this.$emit('add-block', {
        typeBlock: this.typeSelect,
        value: this.value,
        id: Date.now(),
      })

      this.typeSelect = 'title',
      this.value = ''
    }
  },
  components: {
    AppButton,
  }
}
</script>

<style scoped>

</style>