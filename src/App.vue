<template>

 {{ title }}
  <input type="text" ref="abc">
  <button @click="handleEventClick">click</button>

</template>

<script>

export default {
  name: 'App',

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
</style>
