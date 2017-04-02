<template>
<div class="number">
	<div v-if="start" class="number-stage">{{time}}</div>	
	<div v-else class="number-input">
			<input ref="input" type="number" min="00" max="60" v-model="time" @change="handleChange($event.target.value)"/>
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

<style lang="less">
.number {
	width: 10em;
	.number-state {

	}
	.number-input {
		input {
			width: 100%;
			height: 100%;
			text-align: right;
			font-size: 1em;
			font-weight: 400;
			margin: 0;
			padding: 0;
			border: 1px solid #dedede;
			&:focus {
				outline: none;
			}
		}	
	}
}
</style>