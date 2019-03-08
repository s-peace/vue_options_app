<template>
  <div id="app">
    <HelloWorld title="aaaslot">
      <p class="etc">Begin!</p>
      <p slot="a" class="inner">first message</p>
      <p class="etc">Mid</p>
      <p slot="b" class="inner">2nd message</p>
      <p class="etc">End</p>
      <p slot="c" class="inner">3rd message</p>
    </HelloWorld>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
  },
  data: function(){
    return {
      message: "",
      num: 99,
    };
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
h1 {
  color: orange;
}
p {
  margin: 0;
}
</style>
