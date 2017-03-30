<template>
<div class="btn" @click="handleClick">
	<slot></slot>
</div>
</template>

<script>
export default {

  name: 'Button',

  data () {
    return {

    };
  },
  methods: {
  	handleClick(){
  		this.$emit('handleClick')
  	}
  }
};
</script>

<style lang="css" scoped>
.btn {
	
}
</style>