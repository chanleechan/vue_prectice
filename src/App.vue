<template>
<div class = "black-bg" v-if="modalOpen == true">
  <div class = "white-bg">
    <h4>상세 페이지임</h4>
    <p>상세 페이지 내용임</p>
    <button @click="modalOpen =false">닫기</button>
  </div>
</div>
  <div class = "menu">
    <a v-for="(a,i) in menu" :key="(i)">{{a}}</a>
  </div>
  
  
  <!-- <div v-for="(a,i) in products" :key = "i">
    <h4 >{{a}}</h4>
    <p>50 만원</p>
  </div> -->
  
  <div>
    <img src = "./assets/room0.jpg" class = "room-img">
    <h4 @click="modalOpen = true">{{products[0]}}</h4>
    <p>50 만원</p>
    <button @click="increase">허위매물신고</button> <span>신고수 : {{신고수[0]}} </span>
  </div>
  <div>
    <img src = "./assets/room1.jpg" class = "room-img">
    <h4>{{products[1]}}</h4>
    <p>70 만원</p>
    <button @click="increase2">허위매물신고</button> <span>신고수 : {{신고수[1]}} </span>
  </div>
    <div>
    <img src = "./assets/room2.jpg" class = "room-img">
    <h4>{{products[2]}}</h4>
    <p>100 만원</p>
    <button @click="increase3">허위매물신고</button> <span>신고수 : {{신고수[2]}} </span>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      modalOpen : false,
      신고수 : [0,0,0],
      products : ['역삼동원룸','천호동원룸','마포구원룸'],
      menu : ['Home','Products','About'],
    }
  },
  methods : {
    increase(){
      this.신고수[0] +=1;
    },
    increase2(){
      this.신고수[1] +=1;
    },
    increase3(){
      this.신고수[2] +=1;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;

}
.room-img{
  width:100%;
  margin-top:40px;
}
body{
  margin:1
}
div{
  box-sizing: border-box;
}

.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
