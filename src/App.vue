<template>
  <CountDown></CountDown>
  <News></News> 
</template>

<script>
import CountDown from './components/CountDown.vue';
import News from './components/News.vue';


export default {
  name: 'App',
  components: {
    CountDown,
    News
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  background-image: url('./assets/img/bg.png');
  width: 3840px;
  height: 2160px;
  overflow-y: hidden;
}
body,html{
  overflow: hidden;
  width: 100%;
  height: 100%;
  background-color: white;
}
@media screen and (max-width: 1920px) {
  html {
    zoom: 0.5;
  }
}
@media screen and (max-width: 1600px) {
  html {
    zoom: 0.414667;
  }
}
@media screen and (max-height: 749px) {
  html {
    zoom: 0.34525;
  }
}
</style>
