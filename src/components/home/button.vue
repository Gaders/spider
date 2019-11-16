<template>
	<div class="btn" @click="toRules()">
		<span><slot></slot></span>
	</div>
</template>

<script>
	export default {
		methods: {
			toRules() {
				this.$router.push({path: 'rule'})
			}
		},
	}
</script>

<style>
.btn {
    width: 42.8vw;
    height: 9.6vh;
	margin: 0 auto;
	display: flex;
	justify-content: center;
	align-items: center;
	color: #FFFFFF;
	background-image: url("../../assets/images/home/btn2.png");
	background-size: 100% 100%;
}
span {
    position: relative;
    top: 1vh;
}
</style>
