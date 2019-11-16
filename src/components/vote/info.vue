<template>
  <div class="info">
        <p class="live"></p>
        <p class="title">{{}}</p>
        <div class="person">
            <img style="width:10vw;height:5vh;background-color:red">
            <div class="person-info">
                <p>
                    <span>姓名</span>
                    <span class="container">hhhh</span>
                </p>
                <p>
                    <span>学号</span>
                    <span class="container">2121212</span>
                </p>
            </div>
        </div>
        <div class="work">
            <div class="person-work">
                <p>
                    <span>作品</span>
                    <span class="container">《是飒飒》</span>
                </p>
                <p>
                    <span class="person-work-info">内容简介</span>
                    <span class="person-work-container">吼吼吼吼吼吼吼吼吼吼吼吼吼吼吼吼</span>
                </p>
            </div>
        </div>
  </div>
</template>

<script>

export default {
    name: 'info',
    
    components: {
    },
    props: {
        num: Number
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.info {
    width: 85.2vw;
    height: 52.3vh;
    margin: 0 auto;
    background-image: url("../../assets/images/rule/content.png");
    background-size: 100% 100%;
    color: #d0625f;
    font-size: calc(100vw / 750 * 26);
    .container {
        font-family: 'pingfang';
        margin-left: 3vw;
        color: #bf4c49;
        font-size: calc(100vw / 750 * 26);
    }
    .person-work-container {
        font-family: 'pingfang';
        margin-left: 3vw;
        color: #e69693;
        font-size: calc(100vw / 750 * 20);
    }
    .person-work-info {
        color: #d0625f;
    }
    .live {
        width: 10.8vw;
        height: 1.74vh;
        background-size: 100% 100%;
        background-image: url("../../assets/images/vote/live.png");
        position: relative;
        top: 8vh;
        left: 7vw;
    }
    .title {
        text-align: center;
        margin-top: 6.5vh;
        color: #eb7774;
        font-size: calc(100vw / 750 * 34);
    }
    .person {
        width: 50.2vw;
        height: 5vh;
        position: relative;
        left: 12vw;
        margin-top: 3vh;
        img {
            float: left;
            position: relative;
            right: 5vw;
        }
        .person-info {
            float: left;
            position: relative;
            top: -3vh;
            p {
                margin-top: 2vh
            }
        }
    }
    .work {
        margin: 0 auto;
        height: 20vh;
        width: 80vw;
        margin-top: 8vh;
        .person-work {
            position: relative;
            left: 5vw;
            width: 40vw;
            p {
                margin-top: 2vh;
            }
        }
    }
}
</style>