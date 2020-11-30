<template>
  <div id="app">
    <template v-if="!viewModal">
      <modal-button v-on:toggle-modal="showModal"></modal-button>
    </template>
    <template v-else>
      <modal-view v-on:toggle-modal="showModal"></modal-view>
    </template>
  </div>
</template>

<script>
import { ref } from "vue";
import ModalButton from "./components/ModalButton";
import ModalView from "./components/ModalView";

export default {
  name: "App",
  components: {
    ModalButton,
    ModalView,
  },
  setup() {
    let viewModal = ref(false);

    let showModal = () => {
      viewModal.value = !viewModal.value;
    };

    return {
      showModal,
      viewModal,
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
