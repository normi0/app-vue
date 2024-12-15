<template>
  <div class="Backdrop" @click="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </div>
  </div>
</template>
<script>
export default {
  props: ["header", "text", "theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>
<style scoped>
* {
  margin: 0;
  padding: 0;
}
h1 {
  color: rgb(207, 69, 207);
}
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
  color: black;
  text-align: center;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 30px;
}
.Backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw; /* Full viewport width */
  height: 100vh; /* Full viewport height */
  background: rgba(137, 136, 136, 0.5); /* Semi-transparent black */
  z-index: 1; /* Ensure it is on top of other elements */
}

.modal.sale {
  background-color: crimson;
  color: white;
}
</style>
