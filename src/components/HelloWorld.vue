<template>
  <div class="hello">
    <h1>{{title}}</h1>
    <p>{{message}}</p>
    <hr>
    <button v-on:click="doAction">Show/Hide</button>
    <transition name="transit">
      <p v-if="flg" class="trans">Transition</p>
    </transition>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    title: String,
  },
  data: function(){
    return {
      message: "Transition sample!",
      flg: true,
      btn: 'Hide',
    }
  },
  methods: {
    doAction: function(){
      this.flg = !this.flg;
    },
    startAction: function(){
      if(this.flg){
        this.message = 'show////';
      } else {
        this.message = 'hide////';
      }
    },
    endAction: function(){
      if(this.flg){
        this.message = 'show!';
      } else {
        this.message = "hide!";
      }
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 70px;
}
tr td {
  padding: 5px;
  border: 1px solid gray;
}
tr th {
  padding: 5px;
  border: 1px solid gray;
}
tr th.head {
  background-color: black;
  color: white;
}
pre {
  font-size: 14px;
  line-height: 1.25;
}
div.out {
  padding: 5px 0;
  background-color: #eee;
  width: 300px;
  height: 200px;
}
div.mid {
  padding: 5px 0;
  background-color: #ddd;
  width: 200px;
  height: 175px;
}
div.in {
  padding: 5px 0;
  background-color: #ccc;
  width: 100px;
  height: 150px;
}
title {
  padding: 5px 10px;
  color: orange;
}
.area {
  width: 300px;
  height: 100px;
  background-color: #ddd;
  padding: 10px;
  font-size: 20px;
}
.inner {
  color: red;
  font-size: 14px;
}
.etc {
  color: green;
  background-color: #eee;
  font-size: 12px;
  padding: 5px;
}
h1 {
  color: red;
}
.trans {
  width: 150px;
  background-color: red;
  padding: 10px;
  font-size: 20px;
}
.transit-leave-active {
  animation: anim 2.5s reverse;
}
.transit-enter-active {
  animation: anim 5.0s;
}
/* .transit-enter {
  opacity: 0;
}
.transit-enter-to {
  opacity: 1.0;
}
.transit-leave {
  opacity: 1.0;
}
.taransit-leave-to {
  opacity: 0;
}
.tarnsit-enter, .transit-leave-to {
  transform: translateX(200px)
             translateY(-200px)
             scale(5.0)
             rotateY(360deg)
             rotateX(360deg)
             rotateZ(360deg);
  opacity: 0.1;
} */

@keyframes anim {
  0% {
    font-size: 100px;
    transform:  translateX(0px)
                translateY(0px)
                rotateZ(0deg);
    opacity: 1.0;
    background-color: #ddf;
  }
  25% {
    transform:  translateX(250px)
                translateY(0px)
                rotateZ(0deg);
    opacity: 1.0;
    background-color: #fdd;
  }
  50% {
    transform:  translateX(0px)
                translateY(-100px)
                rotateZ(540deg);
    opacity: 1.0;
    background-color: #dfd;
  }
  75% {
    transform:  translateX(250px)
                translateY(-100px)
                rotateZ(540deg);
    opacity: 1.0;
    background-color: #fdf;
  }
  100% {
    transform:  translateX(0px)
                translateY(-200px)
                rotateZ(1080deg);
    opacity: 0;
    background-color: #ffd;
  }
}
</style>