<template>
  <div id="app">
    <h1>{{ message }}</h1>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      message: '',
    };
  },
  mounted() {
    axios.get('http://localhost:3000')
      .then(response => {
        console.log(response.data)
        this.message = response.data.message;
      })
      .catch(error => {
        console.error('Error fetching data:', error);
      });
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
}
</style>