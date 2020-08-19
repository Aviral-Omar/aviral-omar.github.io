<template>
  <aside id="navigation-drawer">
    <nav>
      <ul>
        <li>
          <a
            :class="{ active: active === 'about' }"
            @click="$emit('change-section', 'about')"
          >About Me</a>
        </li>
        <li>
          <a
            :class="{ active: active === 'projects' }"
            @click="$emit('change-section', 'projects')"
          >Projects</a>
        </li>
        <li>
          <a
            :class="{ active: active === 'connect' }"
            @click="$emit('change-section', 'connect')"
          >Connect</a>
        </li>
      </ul>
    </nav>
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
    font-size: 1.5rem;
    background-color: #ffffff;
    display: flex;
    flex-direction: column;
    justify-content: center;
    border-right: 1px solid rgba($color: #000000, $alpha: 0.2);
    box-shadow: 0 2px 2px 2px rgba($color: #000000, $alpha: 0.2);
    height: calc(100vh - 3rem);
    flex-basis: 20rem;
    flex-shrink: 0;
    text-align: center;
    line-height: 2;
    width: 20rem;
    position: fixed;

    nav {
      ul {
        list-style: none;
        margin: 0;
        padding: 0;

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
      }
    }

    @media (min-width: 700px) {
      display: none;
    }
  }
</style>
