<template>
  <div class="container">
    <div class="timers">
      <TimerItem/>
      <div v-for="(timer, index) in timers" :key="index">
        <TimerItem/>
      </div>
      <ButtonAddTimer :add-timer="addTimer"/>
    </div>
  </div>
</template>

<script>
import TimerItem from '../timer/Timer'
import ButtonAddTimer from "../buttonAddTimer/ButtonAddTimer";

export default {
  name: 'TimerPage',
  components: {
    ButtonAddTimer,
    TimerItem
  },
  data() {
    return {
      timers: []
    }
  },
  methods: {
    addTimer() {
      this.timers.push(0);
    },
  }
}
</script>

<style>
@import "./TimersPage.css";
</style>
