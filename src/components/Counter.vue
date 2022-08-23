<template>
  <h2>{{ customTitle }}</h2>
  <p>{{counter}}<sup>2</sup>={{ squareCounter }}</p>
  <div>
    <button @click="increase()">+1</button>
    <button v-on:click="decrease()">-1</button>
  </div>
</template>

<script>
export default {
  props:{
    title:String,
    start:{
      type:Number,
      //required:true,
      default:100,
      validator( value ){
        console.log(value )
        return value>100
      }
    }
  },
  //name:"patito"
  data(){
    return{
      counter:this.start
    }
  },
  methods:{
    getSquareValue(){
      return 'Hola Mundo'
    },
    increase(){
      return this.counter++
    },
    decrease(){
      return this.counter--
    }
  },
  computed:{
    squareCounter(){
      console.log("square computer")
      return this.counter * this.counter;
    },
    customTitle(){
      return this.title?this.title:'Custom'
    }
  }
}
</script>

<style>
  button{
    background-color: aqua;
    border-radius: 5px;
    border: 1px solid white;
    color: white;
    cursor: pointer;
    margin: 0 5px;  
    padding: 5px 15px;
    transition: 0.3s ease-in-out;
  }

  button:hover{
    background-color: aquamarine;
    transition: 0.3s ease-in-out;
  }
</style>