<template>
  <div class="buttonAdd">
    <div class="buttonAdd__svg" @click="addTimer">
      <SvgIcon name="add" color="#9E9E9E"/>
    </div>
  </div>
</template>

<script>
import SvgIcon from "@/components/SvgIcon";

export default {
  name: "ButtonAddTimer",
  components: {SvgIcon},
  props: {
    addTimer: Function,
  }
}

</script>

<style scoped>
@import "./ButtonAddTimer.css";
</style>