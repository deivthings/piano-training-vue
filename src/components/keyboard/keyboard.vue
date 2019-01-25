<template>
  <article class="keyboard">
    <!-- C1 RANGE -->
    <Key type="white" tone="C1"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="D1"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="E1"></Key>
    <Key type="white" tone="F1"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="G1"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="A1"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="B1"></Key>

    <!-- C2 RANGE -->
    <Key type="white" tone="C2"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="D2"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="E2"></Key>
    <Key type="white" tone="F2"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="G2"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="A2"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="B2"></Key>

    <!-- C3 RANGE -->
    <Key type="white" tone="C3"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="D3"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="E3"></Key>
    <Key type="white" tone="F3"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="G3"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="A3"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="B3"></Key>

    <!-- C4 RANGE -->
    <Key type="white" tone="C4"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="D4"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="E4"></Key>
    <Key type="white" tone="F4"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="G4"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="A4"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="B4"></Key>

    <!-- C5 RANGE -->
    <Key type="white" tone="C5"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="D5"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="E5"></Key>
    <Key type="white" tone="F5"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="G5"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="A5"></Key>
    <Key type="black" tone=""></Key>
    <Key type="white" tone="B5"></Key>
  </article>
</template>

<script>
import Key from "./key.vue";

export default {
  components: {
    Key
  }
};
</script>

<style lang="scss">
.keyboard {
  background-color: black;
  display: flex;
  overflow: scroll;
  padding-top: 3px;
}
</style>
