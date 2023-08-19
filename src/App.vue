<template>
 <h1> {{ title }}</h1>

  <input type="text" ref="abc">
  <button @click="handleEventClick">click</button>
<Modal/>
</template>

<script>
 import Modal from "./components/Modal.vue"

 export default {
  name: 'App',
  components:{Modal},
  
  data(){
    return{
      title:"Hallo World"
    }
    
  },
  methods:{

    handleEventClick(){
      console.log("event");
      console.log(this.$refs.abc); 
      this.$refs.abc.classList.add("elham")
    }
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

h1{
  color: #f41137;
}
</style>
