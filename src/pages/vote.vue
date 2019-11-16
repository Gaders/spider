<template>
  <div class="vote">
        <myHeader>参赛作品(12份)</myHeader>
        <book>以下为每位同学的参赛信息与作品，请为他们投出宝贵一票吧！</book>
        <div class="content">
            <div v-for="(item,index) in num" :key = index>
                <info class="info"></info>
            </div>
            <choose class="choose"></choose>
        </div>
        <footer>
            <p>-END-</p>
            <p>COPYRIGHT@红岩网校工作站</p>
        </footer>
  </div>
</template>

<script>
import myHeader from '../components/header.vue'
import book from '../components/vote/book.vue'
import info from '../components/vote/info.vue'
import choose from '../components/vote/choose.vue'



export default {
    name: 'home',
    components: {
        myHeader,
        book,
        info,
        choose,
    },
    data() {
        return {
            num: [1,2,3,4,5,6,7,8,9,10,11,12]
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.vote {
    width: 100vw;
    height: calc(100vh / 390 * 3104);
    background-image: url("../assets/images/vote/bg.png");
    background-size: 100% 100%;
    .content {
        position: relative;
        top: 8vh;
        .info {
            margin-top: 1.8vh;
        }
        .choose {
            margin-top: 1.8vh;
        }
    }
    footer {
        color: #5a9ab2;
        font-size: calc(100vw / 750 * 20);
        text-align: center;
        position: relative;
        top: 10vh;
    }
}

</style>
