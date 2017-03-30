<template>
  <div class="index">
    <div class="timer-group">
      <Timer></Timer>
      <Timer></Timer>
      <Timer></Timer>
    </div>
    <div class="btn-wrap">
      <Button @handleClick="handleClick">{{btnText}}</Button>
    </div>
  </div>
</template>

<script>
import Button from './Button.vue'
import Timer from './Timer.vue'



export default {
  name: 'index',
  component: {
    Button,
    Timer
  },
  data () {
    return {
      btnText:'开始',
      hour: 0,
      minute: 0,
      second: 0
    }
  },
  methods: {
    handleClick(){

    },
    startCountDown(){

    },
    stopCountDown(){

    },
    cancel(){

    },
    clear(){
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
