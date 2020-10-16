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
import { reactive, toRefs } from 'vue';

export default {
  name: 'App',
  setup() {
    const data: DataProps = reactive({
      list: ['a', 'b', 'c'],
      selectList: "",
      selectListFun: (index: number) => {
        data.selectList = data.list[index];
      }
    })
    const refData = toRefs(data)
    return {
      ...refData
    }
  }
};

interface DataProps {
  list: string[];
  selectList: string;
  selectListFun: (index: number) => void;
}
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
