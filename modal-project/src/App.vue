<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#"> Sign up</a>
        <a href="#"> More info</a>
      </template>
      <h1>Ninja Give away</h1>
      <p>Sing up for the Give away</p>
    </modal>
  </div>
  <button @click="toggleModal" v-if="showModal === false">Open Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      header: "Sign up for the giveaway",
      text: "Grab your copy of Vue today!",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style scoped>
#app,
#modals {
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
