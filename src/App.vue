<template>
  <SignupForm />
</template>

<script>
import SignupForm from "./components/SignupForm";

export default {
  name: "App",
  components: {
    SignupForm,
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
  background-color: #f9efefee;
}
</style>
