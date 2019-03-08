<template>
  <div id="app">
    <HelloWorld title="aaaslot">
      <li v-for="obj in slotobjs" v-bind:key="obj.name">
        {{obj.name}}({{obj.mail}})
      </li>
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
      slotobjs:[
        {name:'taro',mail:'taro@yamada'},
        {name:'taro2',mail:'taro@yamada2'},
        {name:'taro3',mail:'taro@yamada3'},
      ]
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
