<template>
  <div id="app">
    <h1>My Vue App with DatePicker Component</h1>
    <DatePickerComponent />
  </div>
</template>

<script>
import DatePickerComponent from './components/DatePickerComponent.vue';
export default {
  name: 'App',
  components: {
    DatePickerComponent
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
}
</style>