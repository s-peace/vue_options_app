<template>
  <div class="hello">
    <h1>{{title}}</h1>
    <pre>{{message}}</pre>
    <hr>
    <div><input type="text"
        v-on:keypress="type"
        @keydown.delete="clear"
        @keydown.space="space"
        @keydown.enter="enter">
    </div>
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
      message: '',
    };
  },
  methods:{
    type: function(event) {
      if(event.key == 'Enter'){return;}
      this.message += event.key + ' ';
      event.target.value = '';
    },
    clear: function(){
      this.message = '';
    },
    space: function(){
      this.message += '_ ';
    },
    enter: function(){
      let res = this.message.split(' ').join('');
      this.message = res.split('_').join(' ');
      event.target.value = '';
    },
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
</style>
