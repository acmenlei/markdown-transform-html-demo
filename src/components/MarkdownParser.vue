<script setup lang='ts'>
import { markdownToHTML } from "markdown-transform-html"
import "markdown-transform-html/lib/styles/index.css"
import "markdown-transform-html/lib/highlight/dark.css"
import { ref, watchEffect } from "vue";

const props = defineProps<{ content: string }>();
const html = ref("");

watchEffect(() => {
  html.value = markdownToHTML(props.content, { highlight: true, lineNumber: true })

})

</script>

<template>
  <div class="markdown-transform-html" v-html="html"></div>
</template>

<style scoped>

</style>