<template>
  <article class="pentagram"  style="font-size:medium">
    <!--pentagram lines-->
    <span></span><span></span><span></span><span></span><span></span>

    <!-- clave de sol -->
    <img class="pentagram__clave" src="../assets/clavesol.svg">

    <!--note over the pentagram-->
    <section class="pentagram__notes-wrapper">
      <div :class="['black-note', note]" v-for="(note,index) in notes" :key="index" :style="{marginLeft:(index * 1) + 'rem'}">
        <!-- <span class="line"></span> -->
        <!-- span.bemol -->
        <!-- span.sostenido -->
      </div>
    </section>
  </article>
</template>

<script>
export default {
  props: {
    notes: { type: Array }
  }
};
</script>

<style lang="scss">
:root {
  --circle-note-height: 0.8em;
  --pentagram-line-height: 1px;
}

/**
* Loop through notes to set bottom position on pentagram
* Notes list goes from high to lower range
* $i highest range from comes down in intervals of .5
* */
$notes: B4 A4 G4 F4 E4 D4 C4 B3 A3 G3 F3 E3 D3 C3;
$i: 5;

@each $note in $notes {
  .#{$note} {
    bottom: calc(var(--circle-note-height) * #{$i});
  }
  $i: $i - 0.5;
}

.pentagram {
  position: relative;
  // span => every pentagram line
  span {
    display: block;
    height: var(--pentagram-line-height);
  }

  @for $i from 1 through 5 {
    span:nth-child(#{$i}) {
      background-color: black;
      margin-bottom: calc(
        var(--circle-note-height) - var(--pentagram-line-height)
      );
    }
  }

  &__clave {
    position: absolute;
    height: 150%;
    left: 0;
    top: -25%;
  }
}

.pentagram__notes-wrapper {
  text-align: center;
  margin-left: -20%;
}

.black-note {
  position: absolute;
  display: inline-block;
  height: 3em;
  width: 0.8em;
  //:before => Stick note
  &:before {
    content: "";
    position: absolute;
    top: 0;
    right: 0;
    width: 0.15em;
    height: 2.5em;
    background-color: black;
    margin: 0 -0.09em -0.25em auto;
  }
  //:after Circle note
  &:after {
    content: "";
    position: absolute;
    bottom: 0;
    right: 0;
    width: inherit;
    height: var(--circle-note-height);
    background-color: black;
    border-radius: 50%;
    transform: skew(-0.1turn, 15deg);
  }
}
</style>
