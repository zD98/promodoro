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

<style lang="less">
.btn {
	width: 100%;
	height: 36px;
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	background: #39f;
	color: #fff;
}
</style>