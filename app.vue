<template>
  <span>Multiline message is:</span>
  <br />
  <textarea v-model="message" placeholder="add multiple lines"> </textarea>
  <div v-if="message" v-for="word in message.split('\n')" style="white-space: pre-line">
    [{{ word.replace(/(^\w+:|^)\/\//, '') }}]({{ word }})
  </div>
</template>

<script setup>
  const links = '';
  const markdown = '';
  import { ref } from 'vue';
  const message = ref('');
</script>

<style scoped>
* {
}
</style>
