<template>
  <div id="app">
    <h3 class='pt-5'>Elevator Exercise</h3>
    <div class="form" v-if="!isStarted">
      <label for="input-live">Enter Number Of Floors:</label>
      <b-form-input type="number" :min="4" v-model="floorsNumber"></b-form-input>
      <label for="input-live">Enter Number Of Elevators</label>
      <b-form-input type="number" :min="1" :max="8" v-model="elevatorNumber"></b-form-input>
      <b-button class='m-4' variant="success" @click="isStarted=true">Start</b-button>
    </div>
    <Elevators :numberOfElevators="parseInt(elevatorNumber)" :numberOfFloors="parseInt(floorsNumber)" v-if="isStarted" />
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
      floorsNumber: 10,
      elevatorNumber: 5
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

.form {
  position: relative;
  width: 25%;
  left: 38%;
}
</style>
