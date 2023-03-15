<template>
  <div>
    <sign-up-form />
  </div>
</template>

<script>
import SignupForm from './components/SignupForm.vue';
export default {
  name: 'App',
  components: {
    'sign-up-form': SignupForm
  }
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
