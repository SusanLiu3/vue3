<template>
 hello world vue3
 <!-- 多事件处理 -->
 <button @click="$emit('click')">点击</button>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      count: 0
    }
  }
}
</script>
