<template>
  <div class="overlay">
    <button @click="closeModal">Close</button>
    <p class="content">
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nobis sit porro
      fugiat natus animi corporis cumque quisquam, similique optio quaerat autem
      culpa! Quibusdam impedit nihil voluptates ullam quis illum quaerat!
    </p>
  </div>
</template>

<script>
export default {
  emits: ['toggle-modal'],
  setup(props, context) {
    let ctx = context;

    let closeModal = () => {
      ctx.emit('toggle-modal');
    }

    return {
      closeModal
    }
  }
};
</script>


<style scoped>
/* Modal Window */
.overlay {
  background-color: rgba(0, 0, 0, 0.7);
  min-height: 100%;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  z-index: 9999;
}

button {
  padding: 3px 4px;
  border: 1px solid black;
  border-radius: 3px;
}

button:active {
  background-color: black;
}

.content {
  width: 100%;
  height: 100%;
  background: #FFFFFF;
  padding: 8px;
  margin: 20px;
  border-radius: 3px;
}
</style>