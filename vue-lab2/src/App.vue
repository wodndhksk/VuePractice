<template>

  <div id="app">

    <div class="black-bg" v-if="modalPage == true">
      <div class="white-bg">
        <h4>상세페이지임</h4>
        <p>상세페이지 내용임</p>
        <button @click="modalPage = false">닫기</button>
      </div>
    </div>

    <div class="menu">
      <a v-for="(temp,i) in menuTest" :key="i">{{ temp }} {{ i }}</a>
    </div>

    

    <div>
      <img src="./assets/room1.jpg" class="room-img">
      <h4>{{ products[0] }}</h4>
      <h4>{{ price1 }} 원</h4>
      <button @click="increase">허위매물 신고</button> 
      <span>신고 수 : {{ report }}</span>
    </div>
    <div>
      <img src="./assets/room2.jpg" class="room-img">
      <h4>{{ products[1] }}</h4>
      <h4>{{ price2 }} 원</h4>
      <!-- <button @click="increase">허위매물 신고</button> 
      <span>신고 수 : {{ report[1] }}</span> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      modalPage : false,
      report : 0,
      menuTest : ['Home', 'Products', 'About'],
      price1 : 60,
      price2 : 70,
      products : ['역삼동원룸', '문정동원룸', '연남동원룸'],
    }
  },
  methods :{
    increase(){
      this.report += 1;
    }
  },
  components: {

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
}
.room-img{
  margin-top: 40px;
  width: 100%;
  height: 400px;
}
body{
  margin : 0
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>