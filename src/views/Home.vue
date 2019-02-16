<template>
  <article class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <HeaderApp></HeaderApp>

    <section class="musical-board">
      <div class="pentagram-wrapper">
        <Pentagram :notes="notesSequence"></Pentagram>
      </div>
    </section>

    <Keyboard @keyPressed="matchSequenceNotes"></Keyboard>

    <Notificator
      :type="notificator.result"
      :visible="notificator.visible"
      @close="notificator.visible = false">
    </Notificator>
  </article>
</template>

<script>
import HeaderApp from "@/components/HeaderApp.vue";
import Pentagram from "@/components/Pentagram.vue";
import Keyboard from "@/components/keyboard/keyboard.vue";
import Notificator from "@/components/Notificator.vue";
import { EventBus } from "../event-bus.js";

export default {
  name: "home",
  components: {
    HeaderApp,
    Pentagram,
    Keyboard,
    Notificator
  },

  data() {
    return {
      /**
       * Random sequece of notes.
       * @ type {Array}
       * notesSequence: ["C3", "D3", "E3", "F3", "G3", "A3", "B3", "C2", "D2", "E2", "F2", "G2", "A2", "B2" ],
       */
      notesSequence: ["C3"],

      /**
       * Current octave range
       * @ type {Number}
       */
      octaveRange: [3, 4],

      /**
       * Global score of the session game
       * Highest puntuation save at localstore
       * @ type {String}
       */
      score: 0,

      /**
       * Fail or success the key stroke
       * @ type {Boolean}
       */
      notificator: {
        visible: false,
        result: false
      }
    };
  },

  methods: {
    /**
     * Test match between key pressed and ramdon note sequence
     * @ param  {[String]} key [key pressed on keyboard]
     */
    matchSequenceNotes(tone) {
      if (this.notesSequence[0] !== tone) {
        this.resultHandler(false);
      } else {
        this.resultHandler(true);
        this.randomSequence();
      }
    },

    /**
     * Generate a sequence of random notes
     * App first versión 0.1 only generate one note
     */
    randomSequence() {
      // First, generate a random octaveRange
      // eslint-disable-next-line
      let octave = Math.floor(Math.random() * ((this.octaveRange[this.octaveRange.length - 1] + 1) - this.octaveRange[0]) + this.octaveRange[0]);

      // Splice note and push another random one
      // Ascii codes to C D E F G A B => 67 68 69 70 71 65 66
      // eslint-disable-next-line
      this.notesSequence.splice(0, 1, String.fromCharCode(Math.random() * (72 - 65) + 65) + octave);
    },

    /**
     * [resultHandler description]
     * @ param {[Boolean]} fail or success
     */
    resultHandler(result) {
      this.notificator.visible = false;
      if (result) {
        EventBus.$emit("onChangeScore", (this.score += 1));
      } else {
        EventBus.$emit("onChangeScore", (this.score -= 1));
      }
      this.notificator.result = result;
      this.notificator.visible = true;
    }
  }
};
</script>

<style lang="scss">
.home {
  min-height: 100vh;
  min-width: 100%;
  display: flex;
  flex-direction: column;
}
.musical-board {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  .pentagram-wrapper {
    width: 80%;
    margin: 0 auto;
    padding: 2rem;
    background-color: white;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
  }
}
</style>
