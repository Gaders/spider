<template>
  <div class="rule">
        <myHeader>活动规则</myHeader>
        <div class="content">
            <div class="header">
                <span :class="{active: nowRule === 'activity' , normal: !nowRule === 'activity'}" @click="changeInfo('activity')">活动介绍</span>
                <span :class="{active: nowRule === 'vote' , normal: !nowRule === 'vote'}" @click="changeInfo('vote')">投票规则</span>
            </div>
            <div v-show="nowRule === 'vote'" class="info">
                <p>
                    1.本投票由投放开始到12月1号零点结束。此投
                    票共十二名选手，将于投票结束后选出获票最多
                    的一名选手，获得本次社团达人秀的“最具人气
                    奖”。此投票每天每人限投三票，可选择投票数
                    量，三票不得投同一名选手。投票结束后暂不可
                    见票数，当天投票结束后统一统计每名选手投票
                    数和排名。（人气）
                </p>
                <p>
                    2.此投票为现场投票，限时五分钟（时间可商量）
                    ，共三位踢馆选手。每人限投一票，投票结束后，
                    得票最多的一位踢馆选手踢馆成功，成为正式的
                    决赛选手之一，继续接下来的表演。（踢馆）
                </p>
            </div>
        </div>
  </div>
</template>

<script>
import myHeader from '../components/header.vue'

export default {
    name: 'home',
    data() {
        return {
            nowRule : 'vote'
        }
    },
    methods: {
        changeInfo(name) {
            this.nowRule = name
        }
    },
    components: {
        myHeader,
    },
    props: {
        msg: String
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.rule {
    width: 100vw;
    height: 100vh;
    background-color: #b2cae4;
}
.content {
    width: 82.9vw;
    height: 52.3vh;
    margin: 0 auto;
    background-image: url("../assets/images/rule/content.png");
    background-size: 100% 100%;
    position: relative;
    top: 6.74vh;
    .header {
        margin: 0 auto;
        width: 45vw;
        display: flex;
        justify-content: space-between;
        position: relative;
        top: 7.13vh;
        .active {
            color: #f56e7d;
        }
        .vote {
            color: #d0625f;
        }
    }
    .info {
        margin: 0 auto;
        width: 65vw;
        font-size: calc(100vw / 750 * 22);
        position: relative;
        top: 10vh;
        font-family: 'pingfang';
        color: #d0625f;
    }
}

</style>