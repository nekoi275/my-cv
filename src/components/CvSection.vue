<template>
  <section id="cv">
    <cv-flip-card v-for="card in cards" :cardInfo="card" :key="card.id"></cv-flip-card>
    <a
      href="https://docs.google.com/document/d/1j-dj_t1xP2WtxRUuSa1_PIdmVqCPjOpgnDapOhp-24I/edit?usp=sharing"
      target="_blank"
    >
      <h1>Google doc CV</h1>
    </a>
  </section>
</template>

<script>
import CvFlipCard from "./CvFlipCard";

export default {
  name: "CvSection",
  components: {
    CvFlipCard
  },
  data: function() {
    return {
      cards: [
        {
          heading: "Technologies",
          data: [
            "HTML",
            "CSS(LESS/Sass/SCSS)",
            "JavaScript",
            "Vue.js",
            "Node.js",
            "Express.js"
          ]
        },
        {
          heading: "Education",
          data: [
            "2020 - OSF Academy JavaScript course",
            "2019 - Odessa National Polytechnic University, IT-school training course “Front-end development. JavaScript”",
            "2010-2015 - National University “Odessa law academy”"
          ]
        },
        {
          heading: "Experience",
          data: [
            "04.2020 - 12.2022 Front-end / JavaScript developer at Peoly",
            "07.2019 - 09.2019 Part-time front-end developer at AVE Startups"
          ]
        }
      ]
    };
  }
};
</script>

<style scoped>
section {
  background-color: var(--main-bg-color);
  height: 100vh;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  padding-top: 120px;
  box-sizing: border-box;
  align-items: center;
}
a {
  width: 300px;
  height: 300px;
  display: block;
  background-color: var(--light-font-color);
  color: var(--main-bg-color);
  text-align: center;
  padding-top: 100px;
  box-sizing: border-box;
  margin: 5px;
}
.flip-card {
  margin: 5px;
}
@media (max-width: 845px) {
  section {
    height: 100%;
    padding-top: 100px;
  }
}
</style>
