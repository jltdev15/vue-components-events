<script setup>
import BlogItemVue from "./BlogItem.vue";
const props = defineProps(['data'])

console.log(props.data);
</script>
<template>

    <div class="flex flex-wrap justify-between gap-6 p-12">
        <BlogItemVue v-for="item in props.data" :key="item.id" :title="item.title" :description="item.description"
            :author="item.author" :duration="item.duration" :category="item.category" />
    </div>

</template>