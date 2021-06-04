<template>
  <FormInput />
</template>

<script>
import FormInput from "./components/FormInput";

export default {
  name: "App",
  components: {
    FormInput,
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
  display: flex;
  justify-content: center;
}

body {
  background-color: #bfb7b7ee;
}
</style>
