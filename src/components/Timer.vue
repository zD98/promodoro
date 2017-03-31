<template>
<div class="number">
	<div v-if="start" class="number-stage">{{time}}</div>	
	<div v-else class="number-input">
			<input ref="input" type="number" min="0" max="60" @change="handleChange($event.target.value)"/>
	</div>
</div>
</template>

<script>
export default {

  name: 'Timer',
  props: {
  	value: {
  		required: true,
  		type: Number,
  		default: 0,
  		validator(val){
  			return val>=0&&val<60
  		}
  	},
  	start: {
  		required: true,
  		type: Boolean,
  		default:false
  	}
  },	
  computed: {
  	time(){
  		return this.value > 9?`${this.value}`:`0${this.value}` 
  	}
  },
  data () {
    return {

    };
  },
  methods:{
  	handleChange(value){
  		let formatValue = value.trim()
  		this.$emit('input', Number(formatValue))
  	}
  }
};
</script>

<style lang="css" scoped>
</style>