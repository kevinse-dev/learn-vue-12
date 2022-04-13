<template>
  <div @click.right="closeModal"  class="backdrop">
    <div :class="theme">
        <h1>{{ props }}</h1>
      <h5>Modal Title</h5>
      <h5>modal content</h5>
      <p>{{ body }}</p>
      <slot>Default Content</slot>
      <div class="actions">
      <slot name="links"></slot>
      </div>
    </div>
    <button @click="$emit('changeTheme')" >Change Theme</button>
  </div>
</template>

<script>
  export default {
    name:'ModalComp',
    props:['props', 'body', 'theme'],
    emits:['changeTheme'],
    methods:{
      closeModal(){
        this.$emit('closeModal')
      }
    }
  }
</script>

<style scoped>
.modal{
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background-color: white;
  border-radius: 10px;
}

.backdrop{
  top: 0%;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
h1{
  color: #03cfb4;
  border: none;
  padding: 0%;
}

.dark{
  background-color:#444;
  color: wheat;
}
.dark h1{
  color: wheat;
}

button{
  padding: 10px 20px;
  border-radius: 4px;
  border: none;
  background: #03cfb4;
  cursor: pointer;
}
</style>