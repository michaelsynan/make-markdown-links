<template>
  <div class="bg-slate-900 min-h-full h-screen text-slate-100 p-4">
    <h1 class="text-3xl font-bold py-2">CREATE MARKDOWN LINKS</h1>
    <div>
      <span>Multiline message is:</span>
      <br />
      <textarea
        v-model="message"
        placeholder="add multiple lines"
        class="w-full"
      >
      </textarea>
      <div
        v-if="message"
        v-for="word in message.split('\n')"
        style="white-space: pre-line"
      >
        [{{ word.replace(/(^\w+:|^)\/\//, '') }}]({{ word }})
      </div>
    </div>
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
