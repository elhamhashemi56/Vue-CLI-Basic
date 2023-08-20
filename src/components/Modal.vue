<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{saleKlass: theme === 'sale' }">
            <h1>{{ headerProps }}</h1>
            <p>{{ textProps }}</p>

            <slot></slot>
            <slot name="links"></slot>
        </div>
        
    </div>
</template>
<!-- ################################################################# -->
<script>
    export default {
        props:["headerProps","textProps","theme"],
        methods:{
            closeModal(){
                this.$emit("close")
            }
        }
    }
</script>
<!-- ################################################################# -->
<style scoped>
.modal{
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background:white;
  border-radius: 10px;
}

.backdrop{
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

h1{
    color: darkgreen;
}

.saleKlass{
    background-color: brown;
    color: white;
}

.saleKlass h1{
    color: white;
}
</style>