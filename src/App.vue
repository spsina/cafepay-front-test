<template>
  <div id="app">
    {{ data }}
  </div>
</template>

<script>

import axios from 'axios'

export default {
  name: 'app',
  data: () => {
    return {
      data: 'hello how arae you'
    }
  }, mounted: function () {
    axios.get('https://cafepay.app/api/v1/cafe/1/menu/list/', {
      headers: {
        Authorization: 'Token c0d98047bc1b36b7731172498781565047d45c96'
      }
    }).then(response => this.data = response.data)
    .catch(error =>console.log(error));
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
