<template>
  <div class="home">
        <div class="content">
            <btnMove>开始投票</btnMove>
            <btn>活动规则</btn>
        </div>
  </div>
</template>

<script>
import btn from '../components/home/button.vue'
import btnMove from '../components/home/buttonMove.vue'

export default {
    name: 'home',
    components: {
        btn,
        btnMove,
    },
    props: {
        msg: String
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.home {
    width: 100vw;
    height: 100vh;
    background-image: url(../assets/images/home/homeBg.png) ;
    background-size: 100% 100%;
}

.content {
    width: 100vw;
    text-align: center;
    position: absolute;
    bottom: 11.7vh;
}
.btnMove {
    margin-bottom: 0.7vh;
    
}
</style>
