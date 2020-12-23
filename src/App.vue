<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <div>value1: {{ value1 }}</div>
  <HelloWorld msg="Hello Vue 3 in CodeSandbox!" @set-value="handleSetValue" />
</template>

<script>
import HelloWorldVue from "./components/HelloWorld.vue";
import { ref } from "vue";
export default {
  name: "App",
  components: {
    HelloWorld: HelloWorldVue,
  },
  setup() {
    const value1 = ref(123);

    const handleSetValue = (val) => {
      console.log('### handler has been triggered.');
      value1.value = val;
    };

    return {
      value1,
      handleSetValue,
    };
  },
};
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
