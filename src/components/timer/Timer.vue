<template>
  <div class="timer">
    <div class="timer__top" :class="{ timer__top_active:isWorked }">
      {{ formatTime }}
    </div>
    <div class="timer__bottom" :class="{ timer__bottom_active:isWorked }">
      <div class="timer__bottomSvg" v-if="isWorked===true" @click="pauseTimer">
        <SvgIcon name="pause" :color="isWorked ? '#FFF' : '#9E9E9E'"/>
      </div>
      <div class="timer__bottomSvg" v-else @click="startTimer">
        <SvgIcon name="play" :color="isWorked ? '#FFF' : '#9E9E9E'"/>
      </div>
      <div class="timer__bottomSvg">
        <SvgIcon @click="stopTimer" name="stop" :color="isWorked ? '#FFF' : '#9E9E9E'"/>
      </div>
    </div>
  </div>
</template>

<script>
import SvgIcon from "@/components/SvgIcon";

export default {
  name: "TimerItem",
  components: {SvgIcon},
  data() {
    return {
      timerId: null,
      isWorked: false,
      hours: 0,
      minutes: 0,
      seconds: 0,
    };
  },
  computed: {
    formatTime() {
      if (this.hours === 0) {
        if (this.minutes === 0) {
          return `${this.seconds}`;
        }
        return `${this.minutes}:${this.seconds}`;
      }
      return `${this.hours}:${this.minutes}:${this.seconds}`;
    },
  },
  methods: {
    startTimer() {
      if (!this.isWorked) {
        this.isWorked = true;
        this.timerId = setInterval(() => {
          this.seconds++
          if (this.seconds === 60) {
            this.seconds = 0
            this.minutes++
          }
          if (this.minutes === 60) {
            this.minutes = 0
            this.hours++
          }
          if (this.hours === 24) {
            this.hours = 0
            this.minutes = 0
            this.seconds = 0
          }
        }, 1000);
      }
    },
    pauseTimer() {
      if (this.isWorked) {
        this.isWorked = false;
        clearInterval(this.timerId);
      }
    },
    stopTimer() {
      this.pauseTimer();
      this.hours = 0
      this.minutes = 0
      this.seconds = 0
    },
  },
}

</script>

<style scoped>
@import "./Timer.css";
</style>