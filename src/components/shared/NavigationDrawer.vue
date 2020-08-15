<template>
  <aside id="navigation-drawer">
    <a
      id="about"
      :class="{ active: active === 'about'}"
      @click="$emit('change-section', 'about')"
    >About Me</a>
    <a
      id="projects"
      :class="{ active: active === 'projects'}"
      @click="$emit('change-section', 'projects')"
    >Projects</a>
    <a
      id="connect"
      :class="{ active: active === 'connect'}"
      @click="$emit('change-section', 'connect')"
    >Connect</a>
  </aside>
</template>

<script>
export default {
  props: {
    activeSection: {
      type: String,
      default: 'about'
    }
  },
  emits: ['change-section'],
  computed: {
    active () {
      return this.activeSection
    }
  }
}
</script>

<style lang="scss" scoped>
#navigation-drawer {
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  border-right: 1px solid rgba($color: #000000, $alpha: 0.2);
  height: calc(100vh - 3rem);
  flex-basis: 20rem;
  flex-shrink: 0;
  text-align: center;
  line-height: 2;

  @media (max-width: 768px) {
    width: 20rem;
    position: fixed;
  }
}

a {
  display: block;
  color: black;

  &.active {
    color: #00afff;
    text-decoration: underline;
  }
  &:hover,
  &:active {
    color: #00afff;
    cursor: pointer;
  }
}
</style>
