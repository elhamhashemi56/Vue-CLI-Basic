<template>
 <h1> {{ title }}</h1>

  <input type="text" ref="abc">
  <button @click="handleEventClick">click</button>
  <p>Welcome ...</p>

  <button @click.alt="changeModalProps">Show Modal(Alt)-Props</button>
  <button @click="changeModalSlot">Show Modal-Slot</button>
  
  <div v-if="showModalProps">
    <Modal :headerProps="header"
           :textProps="text"
           theme="sale"
           @close="changeModalProps"
        />
  </div>

  <div v-if="showModalSlot">
    <Modal @close="changeModalSlot">
      <h1>Modal With Slot</h1>
      <p>Content Modal Slot</p>

      <template v-slot:links >
        <div class="links">
          <a href="">Sign Up</a>
          <a href="">More Info</a>
        </div>
      </template>
    </Modal>
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
      showModalProps:false,
      showModalSlot:false
    }
    
  },
  methods:{

    handleEventClick(){
      console.log("event");
      console.log(this.$refs.abc); 
      this.$refs.abc.classList.add("elham")
    },
    changeModalProps(){
      this.showModalProps = !this.showModalProps
    },
    changeModalSlot(){
      this.showModalSlot =  !this.showModalSlot
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

.links a{
  margin: 0.5rem;
  padding: 10px;
  text-decoration: none;
  border: 1px solid #c6c3c3;
  border-radius: 5px;
  color: black;
}
</style>
