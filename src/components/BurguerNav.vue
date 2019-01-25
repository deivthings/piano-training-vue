<template>
  <div class="burger-nav" @click="toSettings">
    <span></span>
    <span></span>
    <span></span>
  </div>
</template>

<script>
export default {
  methods: {
    toSettings() {
      this.$router.push("/settings");
    }
  }
};
</script>

<style lang="scss">
.burger-nav {
  width: 2rem;
  margin-right: 1rem;
  cursor: pointer;
  span {
    display: block;
    height: 1px;
    background-color: white;
  }
  span:not(:last-child) {
    margin-bottom: 0.5rem;
  }
}
</style>
