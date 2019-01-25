<template>
  <main class="cover">
    <section class="cover__start">
      <h1 class="cover__title">SPEED READING PENTAGRAM</h1>
      <router-link to="/home" tag="button">START</router-link>
    </section>
    <img class="cover__image" src="../assets/clavesol.svg">
  </main>
</template>

<style lang="scss">
.cover {
  overflow: hidden;
  position: relative;
  height: 100vh;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: var(--primary-color);

  &__image {
    position: absolute;
    height: 150%;
    top: -25%;
    left: 0;
    opacity: 0.3;
  }
}

.cover__start {
  position: relative;
  z-index: 1;
  text-align: center;
  max-width: 80%;

  button {
    cursor: pointer;
    padding: 1rem 3rem;
    background-color: yellowgreen;
    border: 0;
    border-radius: 50px;
    color: white;
    font-size: 1.1rem;
    font-weight: bold;
    letter-spacing: 5px;
    &:hover {
      background-color: darken(yellowgreen, 5);
    }
  }
}

.cover__title {
  color: white;
  font-size: 1.5rem;
  letter-spacing: 5px;
  text-align: center;
  padding: 1rem;
  border-top: 1px solid white;
  border-bottom: 1px solid white;
  margin-bottom: 2rem;
}
</style>
