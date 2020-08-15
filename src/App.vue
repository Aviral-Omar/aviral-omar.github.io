<template>
  <Header @toggle-drawer="toggleDrawer" />
  <main>
    <transition name="slide">
      <navigation-drawer
        v-if="isDrawerOpen"
        :active-section="section"
        @change-section="changeSection"
      />
    </transition>
    <transition
      name="slide-fade"
      mode="out-in"
    >
      <component
        :is="activeSection"
        class="section"
        @click="closeDrawer"
      />
    </transition>
  </main>
</template>

<script>
import NavigationDrawer from './components/shared/NavigationDrawer.vue'
import Header from './components/shared/Header.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Connect from './components/Connect.vue'

export default {
  name: 'App',
  components: {
    NavigationDrawer,
    Header,
    About,
    Projects,
    Connect
  },
  data () {
    return {
      isDrawerOpen: !(window.innerWidth < 768),
      activeSection: About,
      section: 'about'
    }
  },
  methods: {
    toggleDrawer () {
      this.isDrawerOpen = !this.isDrawerOpen
    },
    closeDrawer () {
      if (window.innerWidth < 768) {
        this.isDrawerOpen = false
      }
    },
    changeSection (section) {
      if (section === 'about') {
        this.activeSection = About
      } else if (section === 'projects') {
        this.activeSection = Projects
      } else {
        this.activeSection = Connect
      }
      this.section = section
      if (window.innerWidth < 768) {
        this.toggleDrawer()
      }
    }

  }
}
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Quicksand:wght@400&display=swap");
* {
  box-sizing: border-box;
}

html {
  line-height: 1.15;

  body {
    margin: 0;

    #app {
    font-family: 'Quicksand', sans-serif;
    font-size: 1.5rem;
    }

    main {
      display: flex;
      overflow: hidden;
    }

    .section {
      overflow-y: scroll;
      flex-grow: 1;
      text-align: center;
      height: calc(100vh - 3rem);
    }

    .slide-enter-active,
    .slide-leave-active {
      transition: all 0.1s ease-out;
    }

    .slide-enter-from,
    .slide-leave-to {
      transform: translateX(-20rem);
    }

    .slide-fade-enter-active,
    .slide-fade-leave-active {
      transition: all 0.1s ease-out;
    }

    .slide-fade-enter-from {
      transform: translateY(100vh);
      opacity: 0;
    }

    .slide-fade-leave-to {
      transform: translateY(-100vh);
      opacity: 0;
    }
  }
}
</style>
