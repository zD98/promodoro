<template>
<div class="number">
	<div class="number-stage">{{num}}</div>	
	<div class="number-input">
		<input type="number">
	</div>
</div>
</template>

<script>
export default {

  name: 'Timer',
  props: {
  	num: {
  		required: true,
  		type: Number,
  		default: 0
  	}
  },	
  data () {
    return {

    };
  }
};
</script>

<style lang="css" scoped>
</style>