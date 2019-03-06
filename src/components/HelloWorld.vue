<template>
  <div class="hello">
    <h1>{{title}}</h1>
    <p>{{message}}</p>
    <hr>
    <p>val: {{val}}</p>
    <div>*2: <input type="number" v-model="a"></div>
    <div>^2: <input type="number" v-model="b"></div>
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
      message: "check validation",
      val: 0,
    };
  },
  computed: {
    a: {
      get: function(){
        return this.val * 2;
      },
      set: function(value){
        this.val = Math.floor(value / 2);
      },
    },
    b: {
      get: function(){
        return this.val * this.val;
      },
      set: function(value){
        this.val = Math.floor(Math.sqrt(value));
      },
    },
  },
  created: function(){
    this.val = 10;
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
</style>
