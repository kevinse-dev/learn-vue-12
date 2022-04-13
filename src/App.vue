<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <h1>{{ title }}</h1>
  <div v-if="showModal">
  <ModalComp @changeTheme="changeTheme" :theme="dark ? 'modal dark': 'modal' " props="This is Props" :body="text" @closeModal="showModalMethods">
    <template v-slot:links >
      <a href="#">Sign Up</a>
      <a href="#">More Info</a>
    </template>
    <h1>This is Component App</h1>
    <p>hayang dahar euy asa lapar es teh manis cigana ngunah komo jeung randa</p>
  </ModalComp>
  </div>
  <button @click="showModalMethods">Show Modal</button>
</template>

<script>
import ModalComp from './components/ModalComp.vue'

export default {
  name: 'App',
  components: {
    ModalComp
  },
  data(){
    return{
      title:'Vue 3 The Best ',
      text: 'lorem ipsuk asssa kakk hasan bala abala hanet enak pisan cigana cok ',
      dark:false,
      showModal:false,
      }
  },
  methods:{
    changeTheme(){
      return this.dark = !this.dark
    },
    showModalMethods(){
      this.showModal = !this.showModal
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

.actions{
  text-align: center;
  margin: 30px 0 10px 0;
}

.modal .actions a{
  color: #333;
  padding: 8px;
  border: 1px solid #eeee;
  border-radius: 4px;
  text-decoration: none;
  margin: 10px;
}

.modal.dark .actions a {
  color: white;
}

</style>
