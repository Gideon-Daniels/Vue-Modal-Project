<template>
  <h1>Welcome ...</h1>
  <!-- modal one -->
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <!-- named slots -->
        <template v-slot:links>
          <a href="#"> sign up now</a>
          <a href="#"> more info</a>
        </template>
        <!--slot  -->
        <h1>Ninja Giveaway</h1>
        <p>Grab your ninja swag for half price</p>
        
    </Modal>
  </div>
<!-- modal two -->
   <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
        <!--slot  -->
        <h1>Sign up to the newsletter</h1>
        <p>For updates and promo codes!</p>      
    </Modal>
  </div>

  <!-- modal three -->
   <div v-if="showModalThree">
    <Modal @close="toggleModalThree">
        <!--slot  -->
        <h1>Congrats ...</h1>
        <p>Thank you for building this Modal</p>      
    </Modal>
  </div>

  <p>Welcome ...</p>
  <button @click.alt="toggleModal">open  (alt)</button>
  <button @click="toggleModalTwo"> open Modal Two</button>
  <button @click.ctrl="toggleModalThree"> Open Modal Three (ctrl)</button>
</template>

<script>

import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
    data() {
      return {
        title: 'My first Vue App :)',
        showModal: false,
        showModalTwo:false,
        showModalThree:false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    },
    toggleModalThree() {
      this.showModalThree = !this.showModalThree
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
</style>
