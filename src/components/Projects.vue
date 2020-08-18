<template>
  <section id="projects-section">
    <h1>My Projects</h1>
    <div class="card" v-for="project in projects" :key="project">
      <header>
        <div></div>
        <h3>{{ project.title }}</h3>
        <a :href="project.link" target="_blank">
          <img src="../assets/github-logo.png" alt="github" />
        </a>
      </header>
      <p v-for="(line, index) in project.content" :key="index">{{ line }}</p>
    </div>
  </section>
</template>

<script>
export default {
  data () {
    return {
      projects: [
        {
          title: 'This Website',
          content: [
            'This is a personal portfolio website.',
            'I built this while learning front-end development using Vue.js.'
          ],
          link: 'https://github.com/Aviral-Omar/aviral-omar.github.io'
        },
        {
          title: 'Crypt-X',
          content: [
            'This is a basic desktop quizzing app.',
            'I built this in 11th standard using JavaFX to conduct an online treasure-hunt event in my school.'
          ],
          link: 'https://github.com/Aviral-Omar/cryptx'
        },
        {
          title: 'BITS and Pieces',
          content: [
            'This is an app I built using Flutter in my 1st year at college.',
            'It includes a course management system which helps organize your notes and a timetable feature to show your daily schedule',
            'I also included an expense tracker section which can help you manage your finances and shows month-wise expenses and a chart to compare the money spent on different types of purchases.'
          ],
          link: 'https://github.com/Aviral-Omar/bits_and_pieces'
        },
        {
          title: 'Monster Slayer',
          content: [
            'This is a basic browser game built using Vue.js.'
          ],
          link: 'https://github.com/Aviral-Omar/monster_slayer'
        },
        {
          title: 'Train Reservation System',
          content: [
            'This is a terminal-based app built using C as a project for my Computer Programming course.',
            'It was built during the coronavirus pandemic and emulates a train reservation system for migrant labourers.',
            'The data of available trains and booked tickets are read from and written to text files.'
          ],
          link: 'https://github.com/Aviral-Omar/train_reservation_system'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  #projects-section {
    padding: 0 10%;

    .card {
      margin-bottom: 2rem;
      border: 1px solid rgba($color: #000000, $alpha: 0.2);
      border-radius: 5px;
      box-shadow: 2px 2px 2px 2px rgba($color: #000000, $alpha: 0.2);
      padding: 1rem;

      header {
        display: flex;
        justify-content: space-between;

        div {
          width: 2rem;
        }

        h3 {
          margin-top: 0;
          margin-bottom: 1rem;
        }

        img {
          height: 2rem;
          width: 2rem;
        }
      }

      p {
        margin: 0;
      }
    }
    @media (max-width: 700px) {
      padding: 0 5%;
    }
  }
</style>
