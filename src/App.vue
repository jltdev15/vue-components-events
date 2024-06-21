<script setup>
import { computed, ref } from 'vue';
import { BLOG_DATA } from './data'
import BlogList from './components/BlogList.vue'
import BlogForm from './components/BlogForm.vue'

const BLOG_INFO = ref(BLOG_DATA)
const isShow = ref(false)


const createBlogHandler = (payload) => {
  console.log(payload);
  BLOG_INFO.value.push(payload)

}
</script>
<template>
  <div>
    <h1 class="p-6 text-3xl font-bold text-center">Vue 3 Component with props and events</h1>
    <div class="max-w-5xl mx-auto">
      <div class="flex justify-between">
        <h2 class="text-3xl font-bold ">My Blog</h2>
        <button @click="isShow = !isShow" class="px-4 py-2 font-bold text-white rounded hover:bg-blue-700"
          :class="{ 'bg-blue-500 hover:bg-blue-700': !isShow, 'bg-red-500 hover:bg-red-700': isShow }">{{ !isShow ?
            'Show' : 'Close' }}
          Form</button>
      </div>

      <div v-if="isShow" class="py-6">
        <BlogForm :show="isShow" @createPost="createBlogHandler" />
      </div>
      <BlogList :data="BLOG_INFO" />
    </div>
  </div>
</template>