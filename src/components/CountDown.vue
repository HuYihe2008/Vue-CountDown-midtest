<template>
    <div class="text">
        <div class="left-text">
            <img src="../assets/img/left-text.png">
        </div>
        <div class="top-text">
            <img src="../assets/img/countdown-text.png">
        </div>
        <div class="countdown textfamily">
            {{count}}
        </div>
        <div class="neirong">
            <img src="../assets/img/two-white.png" alt="two-white">
        </div>
        <div class="neirong">
            <img src="../assets/img/little-text.png" alt="little-text">
        </div>
        <div class="neirong-2">
            <img src="../assets/img/ren.png" alt="ren">
        </div>
    </div>

</template>
<script>
   export default {
       data() {
           return {            
               count: '', //倒计时
               d: '',
               h: '',
               m: '',
               s: ''
           }
       },
       mounted() {
            this.Time() //调用定时器
       },
       methods: {
           // 天 时 分 秒 格式化函数
            countTime () {
        //获取当前时间
                var date = new Date();
                var now = date.getTime();
        //设置截止时间
                var endDate = new Date("2023-6-15 00:00:00");
                var end = endDate.getTime();
        //时间差
                var leftTime = end - now;
        //定义变量 d,h,m,s保存倒计时的时间
                if (leftTime >= 0) {
                    this.d = Math.floor(leftTime / 1000 / 60 / 60 / 24);
                    this.h = Math.floor(leftTime / 1000 / 60 / 60 % 24);
                    this.m = Math.floor(leftTime / 1000 / 60 % 60);
                    this.s = Math.floor(leftTime / 1000 % 60);
                }
                this.count = this.d + ' 天 ' + this.h + ' 小时 ' + this.m + ' 分 ' + this.s + ' 秒'
                //console.log(this.count);
            },
           //定时器没过1秒参数减1
            Time() {
                setInterval(() => {
                    this.s -= 1
                    this.countTime()
                }, 1000)
            },
       }
   }
</script>
<style scoped>
@font-face {
	font-family:wending;
	src:url("../assets/FZZJ-YRXFTJW.TTF");
}
.text{
    display: flex;
}
.left-text{
    position: relative;
    width: 500px;
    height: 1600px;
    left: -50px;
}
.top-text{
    position: relative;
    width: 1200px;
    height: 400px;
    left: -100px;
    
}
.textfamily {
    font-family:wending;
}
.countdown{
    position: relative;
    width: 2100px;
    height: 260px;
    font-size: 210px ;
    letter-spacing: -20px;
    left: -80px;
    top: 80px;
}
.neirong{
    position: absolute;
    z-index: 2;
}
.neirong-2{
    position: absolute;
    z-index: 1;
}
</style>