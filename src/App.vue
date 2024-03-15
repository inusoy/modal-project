<template>
  <h1>{{ title }}</h1>
  <p>Welcome!</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="http://szczekszczek.pl">Sign up now!</a>
        <a href="http://szczekszczek.pl">More info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </div>
  <div v-if="showModalDark">
    <Modal theme="dark" @close="toggleModal2">
      <template v-slot:logo>
        <img src="./assets/logo.png" alt="logo">
      </template>
      <h1>Our logo!</h1>
      <br>
    </Modal>
  </div>
  <button @click.alt="toggleModal">open modal (alt)</button>
  <button @click="toggleModal2">open dark modal</button>
</template>



<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'My First Vue App',
      showModal: false,
      showModalDark: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModal2() {
      this.showModalDark = !this.showModalDark
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
  border-bottom: 1px solid darkgray;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
