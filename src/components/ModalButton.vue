<template>
  <button @click="openModal">Open</button>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    openModal() {
      //console.log("button event");
      this.$emit("toggle-modal");
    },
  },
};
</script>