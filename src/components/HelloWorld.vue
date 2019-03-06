<template>
  <div class="hello">
    <h1>{{title}}</h1>
    <p>{{message}}</p>
    <hr>
    <div>Value: <input type="number" v-model="val"></div>
    <div style="height:10px;"></div>
    <table>
      <tr>
        <th>add:</th>
        <td>{{add}}</td>
      </tr>
      <tr>
        <th>sub:</th>
        <td>{{sub}}</td>
      </tr>
      <tr>
        <th>multiple:</th>
        <td>{{mult}}</td>
      </tr>
      <tr>
        <th>divide:</th>
        <td>{{div}}</td>
      </tr>
    </table>
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
      add: 0,
      sub: 0,
      mult: 0,
      div: 0,
    };
  },
  watch: {
    val: function(value){
      this.val = value;
      let val = parseInt(value);
      this.add = Math.floor(val + 2);
      this.sub = Math.floor(val - 2);
      this.mult = Math.floor(val * 2);
      this.div = Math.floor(val / 2);
    }
  },
  created: function(){
    this.val = 5;
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
