<template>
  <div class="container">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1 class="display-4">GCC Edit Replacement</h1>
    <div class="row text-start ">
      <div class="col-sm h4">Style Code</div>
      <div class="col-sm h4">Style Name</div>
      <div class="col-sm h4">Image Name</div>
      <div class="col-sm h4">Active</div>
      <div class="col-sm"></div>
    </div>

    <div class="row text-start " v-for="stylecode in stylecodes" :key="stylecode.stylecode" >
      <div class="col-sm"><input type="text" class="form-control" v-model="stylecode.stylecode"/></div>
      <div class="col-sm"><input type="text" class="form-control" v-model="stylecode.stylename" /></div>
      <div class="col-sm"><input type="text" class="form-control" v-model="stylecode.imagename"/></div>
      <div class="col-sm"><input type="text" class="form-control" v-model="stylecode.isactive"/></div>
      <div class="col-sm"><!--<button class="btn btn-sm btn-outline-danger" v-on:click="deletethis(index)">Delete This</button>--></div>
    </div>


    <button class="btn btn-outline-primary">Add</button>
    <button class="btn btn-outline-danger" v-on:click="deletelast()">Delete Last</button>


    <div class="row">
      <div class="col">
{{stylecodes}}
      </div>
    </div>
  </div>
  <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld
  },
  methods: {
    deletelast() {
      this.stylecodes.pop();
    },
    deletethis(index) {
      console.log(index);
      //this.stylecodes.slice(index, index+1);
      delete this.stylecodes[index];
    }
  },
  data() {
    return { 
      stuff: [{sandwich: "subway"},{sandwich: "mike's"}],
      stylecodes: [
        {stylecode:"123", stylename:"Firetruck Red", imagename: "troll.png", isactive: "true"},
        {stylecode:"456", stylename:"Boat Blue", imagename: "goblin.png", isactive: "true"},
        {stylecode:"679", stylename:"Sun Yellow", imagename: "goblin.png", isactive: "true"}
      ]
    };
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
  margin-top: 60px;
}
</style>
