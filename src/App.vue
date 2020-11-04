<template>
  <HelloWorld @click="modifyMsg(), sayHi()" />
  <!-- 指令参数 [title] 动态绑定求值 -->
  <div :[title]="val">
    {{ msg }}
  </div>
  <!-- <button @click="modifyMsg(), sayHi()">点击</button> -->
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  data() {
    return {
      msg: 'vue3 practice',
      title: 'name',
      val: 'lss',
    };
  },
  methods: {
    modifyMsg() {
      this.msg = 'change msg';
    },
    sayHi() {
      console.log('hi');
    },
  },
};
</script>
