<template>
  <transition name="slide">
    <section class="Notificator" :class="[type ? 'success' : 'warning']" v-if="visible">{{ message }}</section>
  </transition>
</template>

<script>
export default {
  props: {
    type: { type: Boolean },
    visible: { type: Boolean, required: false }
  },

  computed: {
    message() {
      return this.type ? "Well Done!!" : "Opps, try again.";
    }
  },

  updated() {
    if (this.visible) {
      setTimeout(() => {
        this.$emit("close");
      }, 1000);
    }
  }
};
</script>

<style lang="scss">
.Notificator {
  width: 100%;
  padding: 1rem;
  color: white;
  position: fixed;
  top: 4rem;
  left: 0;
  z-index: 0;

  &.success {
    background-color: #20b864;
  }

  &.warning {
    background-color: tomato;
  }

  // notification text
  p {
    padding: 0;
    margin: 0;
    text-align: center;
    width: 50%;
    margin: 0 auto;
  }
}
</style>
