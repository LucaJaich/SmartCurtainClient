<template>
  <div id="app">
    <div class="container">
      <div class="row ">
        <div class="col-sm">
          <LedButton></LedButton>
        </div>
        <div class="col-sm">
          <MotorButton></MotorButton>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import LedButton from './components/LedButton.vue'
import MotorButton from './components/MotorButton.vue'
import Vue from 'vue'
import Vue2TouchEvents from 'vue2-touch-events'

Vue.use(Vue2TouchEvents);

export default {
  name: 'app',
  components: {
    LedButton, MotorButton
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
