<script setup lang="ts">
import { ref } from 'vue';
import MarkdonwParser from './components/MarkdownParser.vue'

const defaultMd = `### 1. Javascript Parser 
The default theme is dark, and you can change the styles in the styles section to suit your preferences
\`\`\`js
const anthor = "coderlei";
export default {
  hobby: ['Coding', 'Cook', 'Game'],
  age: 22,
  professional: 'Front-end Engineer',
  email: 'coderleilei@163.com',
  weChat: 'x972761675'
}
\`\`\`

### 2. render table
| prop | type | meaning | mark |
| body | string｜number | 需要解析的内容 | 测试测试 |

### 3. HTML Parser
\`\`\`html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>markdown-transform-html-online-demo</title>
  </head>
  <body>welcome to here！</body>
</html>
\`\`\`

### 4. render no orderlist
- title1
- title2
 - title3
 - title4
- title5

### 5. render orderlist
1. 有序1
2. 有序2
3. 有序3
4. 有序4
 1. 有序4.1
 2. 有序4.2

### 6. render super link
[百度一下](https://baidu.com)

### 7. render image
![图片](https://img0.baidu.com/it/u=4218735100,1707585667&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1664557200&t=7c59d07048bab5fa72df1be136c9aba9)

### 8. render italic
*斜体*

### 9. render strong
**渲染加强字体**

### 10. render single code
\`single code render\`

### over：开发者/归属者
@author：coderlei；wx：x972761675
@repo: https://github.com/acmenlei/markdown-transform-html
`

const content = ref(defaultMd);

</script>

<template>
  <div class="container">
    <div class="left-textarea">
      <textarea v-model="content" id=""></textarea>
    </div>
    <MarkdonwParser class="render-markdown" :content="content" />
  </div>
</template>

<style scoped>
.container {
  display: flex;
  box-sizing: border-box;
}

.container .left-textarea {
  flex: 1;
  height: 100vh;
  border-right: 5px solid #ccc;
}

.container .left-textarea textarea {
  width: 100%;
  resize: none;
  height: 100%;
  border: none;
  outline: none;
  padding: 10px 0 10px 0;
  line-height: 25px;
  font-size: 16px;
}

.container .render-markdown {
  flex: 1;
  height: 100vh;
  overflow-y: auto;
  max-width: 800px;
  padding: 10px;
}
</style>
