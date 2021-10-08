<template>
  <h1>{{ title }}</h1>
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
  <p>Welcome ...</p>
  <button @click.alt="toggleModal">open  (alt)</button>
</template>

<script>

import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
    data() {
      return {
        title: 'My first Vue App :)',
        header: 'Sign up for the Giveaway!',
        text: 'Grab your ninja swag for half the price!',
        showModal: false,
    }
  },
  methods: {
    toggleModal() {
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
