<template>
  <article class="keyboard" ref="keyboard">
    <!-- C1 RANGE -->
    <Key type="white" @keyPressed="keyPressed" tone="C1"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="D1"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="E1"></Key>
    <Key type="white" @keyPressed="keyPressed" tone="F1"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="G1"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="A1"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="B1"></Key>

    <!-- C2 RANGE -->
    <Key type="white" @keyPressed="keyPressed" tone="C2"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="D2"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="E2"></Key>
    <Key type="white" @keyPressed="keyPressed" tone="F2"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="G2"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="A2"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="B2"></Key>

    <!-- C3 RANGE -->
    <Key type="white" @keyPressed="keyPressed" tone="C3"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="D3"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="E3"></Key>
    <Key type="white" @keyPressed="keyPressed" tone="F3"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="G3"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="A3"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="B3"></Key>

    <!-- C4 RANGE -->
    <Key type="white" @keyPressed="keyPressed" tone="C4"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="D4"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="E4"></Key>
    <Key type="white" @keyPressed="keyPressed" tone="F4"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="G4"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="A4"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="B4"></Key>

    <!-- C5 RANGE -->
    <Key type="white" @keyPressed="keyPressed" tone="C5"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="D5"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="E5"></Key>
    <Key type="white" @keyPressed="keyPressed" tone="F5"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="G5"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="A5"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" @keyPressed="keyPressed" tone="B5"></Key>
  </article>
</template>

<script>
import Key from "./key.vue";
import SynthTone from "@/util/audio/SynthTone.js";

export default {
  components: {
    Key
  },

  data() {
    return {
      synthesizer: null
    };
  },

  methods: {
    /**
     * $emit tone to main view app to process if it match
     * Play Sound tone
     * @ param  {[type]} tone [description]
     */
    keyPressed(tone) {
      this.$emit("keyPressed", tone);
      this.synthesizer.playTone(tone);
    }
  },

  /**
   * On Mounted making visible C3
   */
  mounted() {
    this.$refs.keyboard.scrollLeft = 300;
  },

  /**
   * On Created add a Syhtn to our keyboard
   */
  created() {
    this.synthesizer = new SynthTone("triangle");
  }
};
</script>

<style lang="scss">
.keyboard {
  position: relative;
  background-color: var(--dark-color);
  display: flex;
  overflow: scroll;
  padding-top: 3px;
}

@media (min-width: 800px) {
  .keyboard {
    margin: 0 auto;
    width: 80%;
    padding: 5rem 0 1rem 0;
    border-left: 2rem solid var(--dark-color);
    border-right: 2rem solid var(--dark-color);
    margin-bottom: 2rem;
    border-radius: 5px;
  }
}
</style>
