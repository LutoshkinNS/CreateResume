<template>
  <div class="card card-w70">
      <component
          v-for="block in blocks"
          :key="block.id"
          :is="'app-' + block.typeBlock"
          :value="block.value"
          v-if="blocks.length"
      ></component>
    <div v-else>
      <h3>Добавьте первый блок, чтобы увидеть результат</h3>
      <p>Чтобы добавить элемент:</p>
      <ul>
        <li>Выберите тип блока в селекторе</li>
        <li>Нажмите кнопку добавить</li>
      </ul>
      <h4>Примечание:</h4>
      <p>Чтобы добавить аватар необходимо вставить в поле URL адрес изображения (без кавычек)</p>
    </div>
  </div>
</template>

<script>
import AppTitle from "./partsResume/AppTitle";
import AppAvatar from "./partsResume/AppAvatar";
import AppSubtitle from "./partsResume/AppSubtitle";
import AppText from "./partsResume/AppText";

export default {
  props: {
      blocks: {
        type: Array
      },
  },
  computed: {
  },
  components: {
    AppTitle,
    AppAvatar,
    AppSubtitle,
    AppText,
  }
}
</script>

<style scoped>

</style>