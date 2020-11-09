<template>
  <div id="teleport"></div>
  <combinedApi />
  <setup name="setup" :title="curTitle" />
  <!-- 指令参数 [title] 动态绑定求值 -->
  <div :[title]="val" ref="content">
    {{ msg }}
  </div>
  <!-- 多事件处理 -->
  <button @click="modifyMsg(), sayHi()">点击</button>
  <reactive />
  <computed />
  <provide />
  <temp />
  <tele />
  <template v-for="i in list" :key="i">
    <div>{{ i }}</div>
  </template>
  <div id="red" v-bind="{ id: 'yellow' }">v-bind 合并顺序</div>
  <testJsx title="test jsx" />
  <render />
</template>

<script>
import combinedApi from './components/combined/combinedApi.vue';
import setup from './components/combined/setup.vue';
import provide from './components/combined/provide.vue';
import temp from './components/combined/template.vue';
import reactive from './components/reactive/index.vue';
import computed from './components/reactive/computed.vue';
import tele from './components/teleport/index.vue';
import render from './components/render/index.vue';
import { nextTick } from 'vue';
import { testJsx } from './components/jsx/index.js';

export default {
  name: 'App',
  components: {
    combinedApi,
    setup,
    reactive,
    computed,
    provide,
    temp,
    tele,
    testJsx,
    render
  },
  data() {
    return {
      msg: 'vue3 practice',
      title: 'name',
      val: 'lss',
      curTitle: 'setup练习',
      list: ['apple', 'banana'],
    };
  },

  methods: {
    modifyMsg() {
      this.msg = 'change msg';
      nextTick(() => {
        if (this.$refs.content.innerHTML === 'change msg') {
          console.log('dom 修改完成');
        }
      });
    },
    sayHi() {
      console.log('hi');
    },
  },
};
</script>
