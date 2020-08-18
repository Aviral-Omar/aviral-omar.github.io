<template>
  <section id="about-section">
    <img src="../assets/dp.jpg" alt="dp.jpg" />
    <h1>
      Hi! I am
      <span>Aviral Omar!</span>
    </h1>
    <p>I'm a 19-year old second-year student at BITS Pilani, Pilani Campus currently pursuing a Dual Degree (M.Sc.(Hons.) Economics and B.E. Computer Science).</p>
    <p>I began programming at the age of 13 and that is where my love of technology began. I like to regularly keep up with news and advancements in the tech world where something exciting just keeps coming up.</p>
    <p>I have explored several domains of programming such as web development, app development and even desktop app development at one point. In the process, I have learnt and used numerous programming languages like Java, C, C++, Dart, HTML, CSS, JavaScript and Python along with frameworks like JavaFX, Flutter and Vue.js.</p>
    <p>In the future, I would like to venture deeper into the world of backend development as well as native android app development. I would also like to explore newer and ever-expanding technologies such as Machine Learning and Artificial Intelligence.</p>
    <p>Apart from technology, I also love to play and follow basketball🏀️.</p>
  </section>
</template>

<script>
// export default {
//   data () {
//     return {}
//   }
// }
</script>

<style lang="scss" scoped>
  #about-section {
    padding: 2rem 10% 0 10%;

    img {
      border: 2px solid black;
      border-radius: 50%;
      height: 15rem;
      width: 15rem;
    }

    h1 {
      span {
        background: linear-gradient(to right, #00afff, #00ffff, #00afff);
        background-clip: text;
        color: transparent;
      }
    }

    @media (max-width: 700px) {
      padding: 2rem 5% 0 5%;
    }
  }
</style>
