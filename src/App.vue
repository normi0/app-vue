<template>
  <section>
    <h1>{{ title }}</h1>
    <!-- <input type="text" ref="name" /> -->
    <!-- <button @click="handleClick">click Me</button> -->
    <Teleport to=".modals" v-if="showModal">
      <Modal theme="sale" @close="ToggleModal">
        <h1>this is real tryhard shit</h1>
        <p>fuck la life nigga</p>
        <template v-slot:links>
          <a href="https://genshin.hoyoverse.com/fr/">genshin link</a>
          <a href="https://genshin.hoyoverse.com/fr/">genshin link</a>
        </template>
      </Modal>
    </Teleport>
    <Teleport to=".modals" v-if="showModal2">
      <Modal theme="sale" @close="ToggleModal2">
        <h1>namless king</h1>
        <p>this will fuck us all</p>
        <template v-slot:images>
          <img src="@/assets/image/NamlesKing.jpg" alt="NK" />
        </template>
      </Modal>
    </Teleport>
    <button @click.exact="ToggleModal" @click.alt="ToggleModal2">
      open modal
    </button>
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
      showModal2: false,
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
    ToggleModal2() {
      this.showModal2 = !this.showModal2;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app,
.modals {
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
