<template>
  <section class="HeaderApp">
    <BurguerNav></BurguerNav>
    <h1>Speed Reading Pentagram</h1>
    <Score></Score>
  </section>
</template>

<script>
import Score from "@/components/Score.vue";
import BurguerNav from "@/components/BurguerNav.vue";

export default {
  components: {
    Score,
    BurguerNav
  }
};
</script>

<style lang="scss">
:root {
  --header-height: 4rem;
}

.HeaderApp {
  position: relative;
  z-index: 1;
  display: flex;
  align-items: center;
  background-color: var(--primary-color);
  height: var(--header-height);
  padding: 0 1rem;

  h1 {
    font-weight: bold;
    font-size: 1.2rem;
    text-transform: uppercase;
    color: white;
    letter-spacing: 2px;
  }
}
</style>
