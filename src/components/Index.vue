<template>
  <div class="index">
    <div class="timer-group">
      <Timer v-model="hour" :start="start"></Timer>
      <span>:</span>
      <Timer ref="minute" v-model="minute" :start="start"></Timer>
      <span>:</span>
      <Timer v-model="second" :start="start"></Timer>
    </div>
    <div class="btn-wrap">
      <Btn @handleClick="handleClick">{{btnText}}</Btn>
    </div>
  </div>
</template>

<script>
import Btn from './Button.vue'
import Timer from './Timer.vue'


export default {
  name: 'index',
  components: {
    Btn,
    Timer
  },
  data () {
    return {
      start: false,
      btnText:'开始',
      hour: 0,
      minute: 0,
      second: 0,
      timeHandle: false
    }
  },
  methods: {
    handleClick(){
      this.start = true
      this.startCountDown()
    },
    startCountDown(){
      this.timeHandle = setInterval(()=>{
        this.second--
        this.checkTime()
      }, 1000)
    },
    stopCountDown(){
      clearInterval(this.timeHandle)
      this.timeHandle = null
      this.hour = this.minute = this.second = 0
    },
    checkTime(){
      if(this.second < 0&&this.minute==0 && this.hour ==0){
        this.stopCountDown()
        return 
      }
      if(this.second < 0){
        this.second = 59
        this.minute --
      }
      if(this.minute < 0){
        this.minute = 59
        this.hour --
      }
    },
    cancel(){

    },
    clear(){
      
    }
  },
  mounted(){

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
.timer-group{
  margin: 0 auto;
  width: 480px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  font-size: 5em;
}
.btn-wrap {
  width: 300px;
  margin: 0 auto;
}
</style>
