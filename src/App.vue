<template>
  <div id="app">
    <b-container>
      <b-row>
        <b-col  sm="9" offset="1">
          <animal-list />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import AnimalList from './components/AnimalList.vue';

export default {
  name: 'app',
  components: {
    AnimalList
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
