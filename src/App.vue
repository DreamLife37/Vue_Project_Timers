<template>
  <TimerPage/>
</template>

<script>
import TimerPage from "@/components/timersPage/TimerPage";

export default {
  name: 'App',
  components: {
    TimerPage,
  }
}
</script>

<style>
#app {
  font-family: GothamPro, Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #696969;
}

@font-face {
  font-family: 'GothamPro';
  src: local('GothamPro'), local('GothamPro'),
  url('~@/assets/fonts/GothamPro.woff') format('woff');
  font-weight: 100;
  font-style: normal;
}
</style>
