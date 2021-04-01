<template>
  <div id="app">
    <h3 class='pt-5'>Elevator Exercise</h3>
    <b-button class='m-4' variant="success" v-if="!isStarted" @click="isStarted=true">Start</b-button>
    <Elevators v-if="isStarted"/>
  </div>
</template>

<script>
import Elevators from './components/Elevators.vue'

export default {
  name: 'App',
  components: {
    Elevators
  },
  data() {
    return {
      isStarted: false,
    }
  }
}
</script>

<style>
#app {
  text-align: center;
  background-color: #DADADA;
  height: 100vh;
}
</style>
