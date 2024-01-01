<template>
  <h1>{{ title }}</h1>
  <!-- <input type="text" ref="numb" />
  <button @click="handleClick">click me</button> -->
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </Modal>
  </div>
  <button @click="toggleModal">open modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  data() {
    return {
      title: "welcome to vue3",
      header: "Sign up for Giveaway!",
      text: "grab your ninja swipee for half the price",
      showModal: false,
    };
  },
  methods: {
    handleClick() {
      const myInput = this.$refs.numb;
      console.log(myInput);
      myInput.classList.add("active");
      myInput.focus();
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
  components: { Modal },
};
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
</style>
