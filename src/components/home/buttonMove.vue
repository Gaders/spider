<template>
	<div class="btn-move" :class="{move: moveActive}" @click="toVote()">
		<span><slot></slot></span>
	</div>
</template>

<script>
	export default {
		data() {
            return {
                moveActive: false
            }
        },
		methods: {
			toVote() {
                this.moveActive = true 
                setTimeout(() => {
                    this.moveActive = false
                    this.$router.push({path: 'vote'})
                },500)
            },
		},
	}
</script>

<style>
	.btn-move {
        width: 42.8vw;
        height: 9.6vh;
		margin: 0 auto;
        margin-bottom: 0.7vh;
		display: flex;
		justify-content: center;
		align-items: center;
		color: #FFFFFF;
		background-image: url("../../assets/images/home/btn1.png");
		background-size: 100% 100%;
		background-position: 0 0;
        
	}
	.move {
		animation: move 0.5s linear;
	}
    span {
        position: relative;
        top: 1vh;
    }
	@keyframes move{
		0%{
			position: relative;
			top: 0px;
		}
		25%{
			position: relative;
			top: -20px;
		}
		50%{
			position: relative;
			top: 0px;
		}
		75%{
			position: relative;
			top: 20px;
		}
		100% {
			position: relative;
			top: 0px;
		}
	}
</style>
