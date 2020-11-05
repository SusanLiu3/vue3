<template>
  <combinedApi />
  <setup name="setup" :title="curTitle" />
  <!-- 指令参数 [title] 动态绑定求值 -->
  <div :[title]="val">
    {{ msg }}
  </div>
  <!-- 多事件处理 -->
  <button @click="modifyMsg(), sayHi()">点击</button>
  <reactive />
  <reacComputed />
</template>

<script>
import combinedApi from './components/combined/combinedApi.vue';
import setup from './components/combined/setup.vue';
import reactive from './components/reactive/index.vue';
import reacComputed from './components/reactive/computed.vue';

export default {
  name: 'App',
  components: {
    combinedApi,
    setup,
    reactive,
    reacComputed
  },
  data() {
    return {
      msg: 'vue3 practice',
      title: 'name',
      val: 'lss',
      curTitle: 'setup练习',
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
