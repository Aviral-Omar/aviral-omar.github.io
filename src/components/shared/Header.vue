<template>
  <header class="navigation-bar">
    <div
      id="hamburger-icon"
      @click="$emit('toggle-drawer')"
    >
      <img
        src="../../assets/hamburger-icon.png"
        alt="Could not load asset!"
      >
    </div>
  </header>
</template>

<script>
export default {
  emits: ['toggle-drawer'],
  data () {
    return {}
  }
}
</script>

<style lang="scss" scoped>
  .navigation-bar {
    display: flex;
    justify-content: flex-start;
    padding: 0.5rem;
    height: 3rem;
    width: 100%;
    background: linear-gradient(to right, #00afff, #00ffff);

    #hamburger-icon {
      height: 2rem;
      width: 2rem;

      img {
        height: 100%;
        width: 100%;
      }

      @media(min-width: 768px) {
        display: none;
      }
    }
  }
</style>
