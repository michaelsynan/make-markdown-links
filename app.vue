<template>
  <div class="bg-slate-900 min-h-full h-screen text-slate-100">
    <theHeader />
    <div>
      <label class="text-lg" for="theMessage">Paste your links</label>
      <br />
      <textarea
        v-model="message"
        placeholder="add multiple lines"
        class="w-full bg-stone-700"
        name="theMessage"
      >
      </textarea>
      <div class="flex items-center mb-4">
        <input
          id="default-checkbox"
          type="checkbox"
          value=""
          v-model="bulletpoints"
          @onclick="bulletpoints != bulletpoints"
          class="
            w-4
            h-4
            text-blue-600
            bg-gray-100
            border-gray-300
            rounded
            focus:ring-blue-500
            dark:focus:ring-blue-600 dark:ring-offset-gray-800
            focus:ring-2
            dark:bg-gray-700 dark:border-gray-600
          "
        />
        <label for="default-checkbox" class="ml-2 text-sm font-medium"
          >Bullet points</label
        >
      </div>
      <div
        v-if="message"
        v-for="word in message.split('\n')"
        style="white-space: pre-line"
      >
        <span v-if="bulletpoints">- </span>
        <span class="text-stone-500">[</span>
        {{ word.replace(/(^\w+:|^)\/\//, '') }}
        <span class="text-stone-500">]</span>
        <span class="text-stone-500">(</span>
        {{ word }}
        <span class="text-stone-500">)</span>
      </div>
    </div>
  </div>
</template>

<script setup>
const links = '';
const bulletpoints = false;
const markdown = '';
import { ref } from 'vue';
const message = ref('');
</script>

<style scoped>
* {
}
</style>
