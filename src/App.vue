<template>


  <radio-input-component @customChange="callback"/>
</template>

<script>

import RadioInputComponent from "@/components/radioInputComponent";
export default {
  callback : "",
  name: 'App',
  components: {
    RadioInputComponent

  },


  methods : {
    callback(event) {
      console.log(event)
    }
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
