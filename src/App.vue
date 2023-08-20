<template>
 <h1> {{ title }}</h1>

  <input type="text" ref="abc">
  <button @click="handleEventClick">click</button>
  <p>Welcome ...</p>

  <button @click.alt="changeModal">Show Modal(Alt)</button>
  
  <div v-if="showModal">
    <Modal :headerProps="header"
         :textProps="text"
         theme="sale"
         @close="changeModal"
        />
  </div>
  

</template>
<!-- ################################################################# -->
<script>
 import Modal from "./components/Modal.vue"

 export default {
  name: 'App',
  components:{Modal},
  
  data(){
    return{
      title:"Hallo World",
      header:"Title Modal",
      text:"Modal content",
      showModal:false
    }
    
  },
  methods:{

    handleEventClick(){
      console.log("event");
      console.log(this.$refs.abc); 
      this.$refs.abc.classList.add("elham")
    },
    changeModal(){
      this.showModal = !this.showModal
    }
  }
  
  
}
</script>
<!-- ################################################################# -->

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
