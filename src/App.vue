<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>

  <div v-if="showModal">
  <Modal theme="" @close="toggleModal">
    <template v-slot:links>
      <a href="#">Sign up now!</a>
      <a href="#">More info</a>
    </template>
    <h1>Alvunera Giveaway!</h1>
    <p>Grab your Nera's merchandise for half price!</p>
  </Modal>
  </div>
  
  <div v-if="showModal2">
  <Modal theme="" @close="toggleModal2">
     <template v-slot:links>
      <a href="#">Daftar yuk</a>
      <a href="#">Info selengkapnya</a>
    </template>
    <h1>Alvunera bagi bagi sesuatu!</h1>
    <p>Dapatkan pernak pernik dari Nera sekarang!</p>
  </Modal>
  </div>
  <button @click.alt="toggleModal">Inggris (alt)</button>
  <button @click="toggleModal2">Indonesia</button>
</template>


<script>
import Modal from './components/Modal'
export default {
  name: 'App',
  components: { Modal },
  data(){
    return {
      title: 'My First Vue App :)',
      header: 'Sign up for Giveaway!',
      text: 'Grab yout packet for half price!',
      showModal: false,
      showModal2: false
    }
  },
  methods: {
    toggleModal(){
        this.showModal = !this.showModal
      },
    toggleModal2(){
        this.showModal2 = !this.showModal2
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
button {
  background: #bbb;
  padding: 10px;
  border: none;
  border-radius: 4px;
  margin: 10px;
  font-size: 16px;
  color: #333;
}
</style>
