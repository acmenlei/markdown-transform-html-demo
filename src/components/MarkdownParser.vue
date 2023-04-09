<script setup lang='ts'>
import "markdown-transform-html/lib/styles/index.css"
import { markdownToHTML, reHighlight } from 'markdown-transform-html'
import { onMounted, ref, watchEffect } from "vue";

const props = defineProps<{ content: string }>();
const container = ref();

onMounted(() => {
  watchEffect(() => {
    container.value.innerHTML = markdownToHTML(props.content, { highlight: true, lineNumber: true, xss: false })
    reHighlight();
  })
})

</script>

<template>
  <div class="markdown-transform-html" ref="container"></div>
</template>

<style scoped></style>