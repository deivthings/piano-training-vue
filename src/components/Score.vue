<template>
  <section class="score">
    <h4 class="score__title">SCORE</h4>
    <h3 class="score__value">{{score}}</h3>
  </section>
</template>

<script>
import { EventBus } from "../event-bus.js";

export default {
  data() {
    return {
      score: 0
    };
  },

  /**
   * On created register onChangeScore event in order to paint the new score value.
   */
  created() {
    EventBus.$on("onChangeScore", score => {
      this.score = score;
    });
  }
};
</script>

<style lang="scss">
.score {
  margin-left: auto;
  display: flex;
  align-items: inherit;

  &__title {
    margin-right: 0.5rem;
    color: white;
  }

  &__value {
    background-color: white;
    padding: 0.5rem;
    font-weight: bold;
    border-radius: 4px;
  }
}
</style>
