<script setup>
import { tagColor } from '../helper/helper'
const props = defineProps(['title', 'description', 'author', 'duration', 'category'])
console.log(tagColor('Tech'));
</script>
<template>

    <article class="w-3/12 shadow">
        <h3 class="p-3 text-2xl font-bold bg-green-600 text-gray-50">{{ props.title }}</h3>
        <p class="p-3">{{ props.description }}.</p>
        <div class="flex items-center justify-between p-3">
            <span class="text-xs text-gray-400">{{ props.author }}</span>
            <p class="text-xs text-right text-gray-400">{{ props.duration }} mins read</p>
        </div>
        <div class="flex gap-3 p-3 bg-gray-400 text-gray-50">
            <p :class="tagColor(tag)" v-for="tag in props.category" :key="tag.id" class="inline-block p-2 rounded-2xl">
                {{
                    tag
                }}</p>

        </div>

    </article>

</template>