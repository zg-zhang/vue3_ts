<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h2>666</h2>
    <p>选择</p>
  </div>
  <div>
    <button
        v-for="(item, index) in list"
        v-bind:key="index"
        @click="selectListFun(index)"
    >
      {{ index }} : {{ item }}
    </button>
  </div>
  <div>你选择了 {{ selectList }} </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'App',
  setup() {
    const list = ref(['a', 'b', 'c']);
    const selectList = ref("");
    const selectListFun = (index: number) => {
      selectList.value = list.value[index];
    }
    return {
      list,
      selectList,
      selectListFun
    }
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
