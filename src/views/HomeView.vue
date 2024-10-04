<script setup>
import { ref } from 'vue';
import searchItems from '../components/searchItems.vue'

const search = ref('')

const text = ref("Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum")
</script>

<template>
  <main>
    <div>
      <input type="search" class="style-input" v-model="search">
    </div>
    <searchItems :text="text" :search="search" effect='sexiness' />
  </main>
</template>
<style>
.style-input {
  border: 1px solid #ddd;
  outline: none !important;
  padding: 10px;
  height: 40px;
  width: 350px;
  border-radius: 8px;
  margin-bottom: 15px;
}
</style>