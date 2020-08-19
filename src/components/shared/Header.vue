<template>
  <header class="main-header">
    <div id="hamburger-icon" @click="$emit('toggle-drawer')">
      <img src="../../assets/hamburger-icon.png" alt="Could not load asset!" />
    </div>
    <nav id="main-navigation">
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
  </header>
</template>

<script>
export default {
  props: {
    activeSection: {
      type: String,
      default: 'about'
    }
  },
  emits: ['toggle-drawer', 'change-section'],
  computed: {
    active () {
      return this.activeSection
    }
  }
}
</script>

<style lang="scss" scoped>
  .main-header {
    font-size: 1.5rem;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding: 0.5rem;
    height: 3rem;
    width: 100%;
    background: linear-gradient(to right, #00afff, #00ffff 50%, #00afff);
    box-shadow: 2px 0 2px 2px rgba($color: #000000, $alpha: 0.2);

    #hamburger-icon {
      height: 2rem;
      width: 2rem;

      img {
        height: 100%;
        width: 100%;
      }

      @media (min-width: 700px) {
        display: none;
      }
    }

    #main-navigation {
      color: white;

      ul {
        margin: 0;
        padding: 0;
        display: inline-flex;
        list-style: none;

        li {
          a {
            padding: 0 1rem;
            display: block;
            color: black;

            &.active {
              color: #ffffff;
              border: #ffffff 2px solid;
              border-radius: 5px;
            }

            &:hover,
            &:active {
              color: #ffffff;
              cursor: pointer;
            }
          }
        }
      }

      @media (max-width: 700px) {
        display: none;
      }
    }

    @media (min-width: 700px) {
      justify-content: flex-end;
    }
  }
</style>
