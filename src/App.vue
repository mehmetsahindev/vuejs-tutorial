<template>
  <h1>{{ title }}</h1>
  <button @click="toggleModal">Sign Up</button>
  <teleport to="#modals" v-if="showModal">
    <Modal title="Sign Up" text="Sign Up and start your journey." @close-modal="toggleModal">
    <form action="">
      <div class="input-group">
        <label>Name*</label>
        <input type="text" name="name">
      </div>
      <div class="input-group">
        <label>Email*</label>
        <input type="text" name="email">
      </div>
    </form>

    <template v-slot:actions>
      <a href="#">Sing Up</a>
      <a href="#">More Info</a>
    </template>
  </Modal>
  </teleport>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  data() {
    return {
      title: "Hello World!",
      showModal: false
    }
  },
  components: { Modal },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    }
  }
}
</script>

<style>
#app, #modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<style scoped>
  button {
    background-color: crimson;
    color: #ffffff;
    padding: 5px 10px;
    border-radius: 15px;
    border: none;
  }
</style>
