<template>
<span>

  <svg v-if="name==='play'" width="17" height="20" viewBox="0 0 17 20" v-bind:fill="color" xmlns="http://www.w3.org/2000/svg">
<path d="M0 20V0L17 10L0 20Z" fill="#9E9E9E"/>
</svg>

   <svg v-if="name==='stop'" width="20" height="20" viewBox="0 0 20 20" v-bind:fill="color" xmlns="http://www.w3.org/2000/svg">
<rect width="20" height="20" v-bind:fill="color"/>
</svg>

  <svg v-if="name==='pause'" width="10" height="20" viewBox="0 0 10 20" v-bind:fill="color" xmlns="http://www.w3.org/2000/svg">
<rect x="7" width="3" height="20" v-bind:fill="color"/>
<rect width="3" height="20" v-bind:fill="color"/>
</svg>

  <svg v-if="name==='add'" width="20" height="20" viewBox="0 0 20 20" v-bind:fill="color" xmlns="http://www.w3.org/2000/svg">
<rect x="8.5" width="3" height="20" v-bind:fill="color"/>
<rect y="11.5" width="3" height="20" transform="rotate(-90 0 11.5)" v-bind:fill="color"/>
</svg>

</span>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true
    },
    color: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>

</style>