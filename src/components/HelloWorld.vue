<template>
  <div class="hello">
    <h1>{{title}}</h1>
    <pre v-on:click="clear">{{message}}</pre>
    <hr>
    <div id="out" class="out" v-on:click="a_event">A
      <div id="mid" class="mid" v-on:click.self="b_event">B
        <div id="in" class="in" v-on:click="c_event">C</div>
      </div>
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
    a_event: function(event){
      this.message += "A_Event [" + event.target.id 
                      + ' → ' + event.currentTarget .id + "]\n";
    },
    b_event: function(event){
      this.message += "B_Event [" + event.target.id 
                      + ' → ' + event.currentTarget .id + "]\n";
    },
    c_event: function(event){
      this.message += "C_Event [" + event.target.id 
                      + ' → ' + event.currentTarget .id + "]\n";
    },
    clear: function() {
      this.message = '';
    }
  },
  mounted: function(){
    this.message = "";
  }
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
</style>
