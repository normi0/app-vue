<template>
  <section>
    <h1>{{ title }}</h1>
    <!-- <input type="text" ref="name" /> -->
    <!-- <button @click="handleClick">click Me</button> -->
    <div v-if="showModal">
      <Modal theme="not sale" @close="ToggleModal">
        <h1>this is real tryhard shit</h1>
        <p>fuck la life nigga</p>

        <template v-slot:links>
          <a href="https://genshin.hoyoverse.com/fr/">genshin link for fun </a>
        </template>
      </Modal>
    </div>
    <button @click="ToggleModal">open modal</button>
  </section>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "first vue App;)",
      header: "welcome to my world",
      showModal: false,
      text: "write something here",
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
    },
    ToggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  text-align: center;
  color: rgb(2, 2, 70);
  margin-top: 60px;
}
h1 {
  display: flex;
  justify-content: center;
  align-content: center;
  border-bottom: 1px solid green;
  padding-bottom: 10px;
}
</style>
