<template>
  <div class="choose">
        <p class="live"></p>
        <p class="title">投票环节</p>
        <p class="side-title">(每天最多投三张票)</p>
        <div id="main" style="width: 100%;height: 80%"  v-if="status === 'show'"></div>
        <div class="content" v-if="status === 'choose'">
            <div v-for="(item,index) in number" :key="index">
                <label class='lab' >
                    <input type='checkbox' class='inputStatus' name="v1" @click="chooseThis(index)" >
                    <span class='inputStyle2' :class="{isChecked: chooseStatus[index]}" ></span>
                    <span class="number">{{number[index]}}号选手</span>
                </label>
            </div>
        </div>
        <div class="footer" v-if="status === 'choose'">
            <div class="btn" @click="vote()"></div>
            <span style="display:none">{{checkList}}</span>
        </div>
        <div v-if="tip" :class="{tipLoading: isLoading,tipSuccess: !isLoading}"></div>
  </div>
</template>

<script>
import echarts from 'echarts'
import { setTimeout } from 'timers'
export default {
    name: 'choose',
    data() {
        return {
            number: [1,2,3,4,5,6,7,8,9,10,11,12],
            checkList: [],
            chooseStatus: [0,0,0,0,0,0,0,0,0,0,0,0],
            voteAbled: 3,
            status: "choose",
            tip: false,
            isLoading: true,
        }
    },
    mounted() {
        
    },
    methods: {
        chooseThis(index) {
            for(let i = 0; i <= this.checkList.length + 1; i++) {
                if(this.checkList[i] == index + 1) {
                    this.checkList.splice(i,1)
                    this.chooseStatus[index] = 0
                    return
                }
            }
            if(this.checkList.length < this.voteAbled) {
                this.checkList.push(index + 1)
                this.chooseStatus[index] === 0 ? this.chooseStatus[index] = 1 : this.chooseStatus[index] = 0
            }
        },
        vote() {
            this.status = 'show'
            this.tip = true
            setTimeout(() => {
                this.isLoading = false
                
            },1000)
            setTimeout(() => {
                this.showchart()
                this.tip = false
            },2000)
        },
        showchart(){
            var myChart = echarts.init(document.getElementById('main'));
            var option = {
                title : {
                    text: '',
                    subtext: ''
                },
                tooltip : {
                    trigger: 'item'  //悬浮提示框不显示
                },
                grid:{   //绘图区调整
                    x:80,  //左留白
                    x2:80, 
                    y:20, //上留白
                },
                xAxis : [
                    {
                        show:false,
                        type : 'value',
                        boundaryGap : [0, 0],
                        position: 'top'
                    }
                ],
                yAxis : [
                    {
                        type : 'category',
                        data : ['巴西','印尼','美国','印度','中国','内蒙古','a','b','c','d','中国','内蒙古'],
                        axisLine:{show:false},     //坐标轴
                        axisTick:[{    //坐标轴小标记
                            show:false
                        }],
                        axisLabel:{
                            textStyle:{
                                fontSize:'calc(100vw / 750 * 26)',
                                color:'#bf4c49',

                            }
                        }
                    }
                ],
                series : [
                    {
                        name:'',
                        type:'bar',
                        tooltip:{show:false},
                        barGap:'-50%',
                         //最小柱高
                        barWidth: 10,  //柱宽度
                        barMaxWidth:80,
                        barMaxHeight:50,  //最大柱宽度
                        data:[1, 100, 100, 400, 0, 300,100,200,105,100,150,100],
                        itemStyle:{
                            normal:{    //柱状图颜色
                                color:'#ff6600',
                                label:{
                                    show: true,   //显示文本
                                    position: 'right',  //数据值位置
                                    textStyle:{
                                        color:'#e69693',
                                        fontSize:'calc(100vw / 750 * 20)',
                                        fontFamily: 'pingfang',
                                    }
                                }
                            }
                        }
                    }
                ]
            };
            myChart.setOption(option);
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.choose {
    width: 85.2vw;
    height: 109.28vh;
    margin: 0 auto;
    background-image: url("../../assets/images/vote/chooseBg.png");
    background-size: 100% 100%;
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
    .side-title {
        text-align: center;
        font-family: 'pingfang';
        color: #e37c79;
        font-size: calc(100vw / 750 * 26);
    }
    .content {
        .lab {  
            display: flex;
            margin-top: 2.57vh;
            position: relative;
            left: 2.2vw;
        }
        .inputStatus{
            opacity: 0;
        }
        .number {
            margin-left: 8vw;
            position: relative;
            top: 1.2vh;
            font-family: "pingfang";
            font-size: calc(100vw / 750 * 26);
            color: #bf4c49;
        }
        .inputStyle2{
            position: relative;
            display: block;
            left: 2vw;
            bottom: 2vh;
            width: 6vw;
            height: 3.731vh;
            background-image: url("../../assets/images/vote/label.png");
            background-size: 100% 100%
        }  
        .isChecked {
            background: url("../../assets/images/vote/labelCilck.png");
            background-size: 100% 100%
        }
    }
    .btn {
        position: relative;
        top: 5.2334vh;
        width: 22.933333vw;
        height: 9.28689vh;
        background-image: url("../../assets/images/vote/vote.png")
    }
}
#main {
    font-family: 'pingfang';
    font-size: calc(100vw / 750 * 20);
}
.tipLoading {
    width: 40.4vw;
    height: 10.53vh;
    background-image: url("../../assets/images/vote/loading.png");
    background-size: 100% 100%;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-20.2vw,-5.265vh)
}
.tipSuccess {
    width: 40.4vw;
    height: 10.53vh;
    background-image: url("../../assets/images/vote/success.png");
    background-size: 100% 100%;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-20.2vw,-5.265vh)
}
</style>