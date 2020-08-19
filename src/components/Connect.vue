<template>
  <section id="connect-section">
    <h1>Connect</h1>
    <nav>
      <a
        class="website"
        v-for="website in websites"
        :key="website.id"
        :href="website.link"
        target="_blank"
      >
        <img :src="website.logo" alt="logo" />
        <h3>{{ website.id }}</h3>
      </a>
    </nav>
  </section>
</template>

<script>
export default {
  data () {
    return {
      websites: [
        {
          logo: require('../assets/gmail-logo.png'),
          link: 'javascript: void(0)',
          id: 'aviralomar0301@gmail.com'
        },
        {
          logo: require('../assets/github-logo.png'),
          link: 'https://github.com/Aviral-Omar',
          id: 'Aviral-Omar'
        },
        {
          logo: require('../assets/linkedin-logo.png'),
          link: 'https://www.linkedin.com/in/aviral-omar-881244197',
          id: 'Aviral Omar'
        },
        {
          logo: require('../assets/instagram-logo.png'),
          link: 'https://instagram.com/aero_0301',
          id: '@aero_0301'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  #connect-section {
    padding: 0 auto 1rem auto;
    display: flex;
    flex-direction: column;
    align-items: center;

    nav {
      width: min-content;

      .website {
        display: flex;
        justify-content: flex-start;
        text-decoration: none;
        color: #000000;
        align-items: center;

        h3 {
          font-size: 1.3rem;
          margin: 1rem 0 1rem 1rem;
        }

        img {
          width: 2rem;
        }
      }
    }

    @media (max-width: 700px) {
      padding: 0 5%;
    }
  }
</style>
