<template>
  <div class="Backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot></slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
      <div class="image-container">
        <slot name="images"></slot>
      </div>
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
<style>
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
.modal .actions {
  text-align: center;
  margin: 30px 0 10px 0;
  color: darkblue;
}
.modal .actions a {
  color: white;
  padding: 8px;
  border: 1px solid white;
  border-radius: 4px;
  text-decoration: none;
  margin: 10px;
}
.modal .image-container {
  width: 200px;
  height: 200px;
  margin: 0 auto;
  background: lightblue;
  border: 2px solid #ccc;
  border-radius: 10px;
  display: flex;
  justify-content: center;
  align-content: center;
  overflow: hidden;
}
.modal .image-container img {
  max-width: 100%;
  max-height: 100%;
  object-fit: cover;
}
.modal h1 {
  color: lightseagreen;
  border: none;
  padding: 0;
}
.modal p {
  font-style: normal;
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
.modal.sale h1 {
  color: white;
}
</style>
