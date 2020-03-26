<template>
  <section id="cv">
    <cv-flip-card v-for="card in cards" :cardInfo="card" :key="card.id"></cv-flip-card>
    <a
      href="https://docs.google.com/document/d/10xQRhA28LRYPmtwvQRYwCc-DMeyxKDz4-Hbim1ybITA/edit?usp=sharing"
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
            "jQuery",
            "Vue.js",
            "Express.js"
          ]
        },
        {
          heading: "Education",
          data: [
            "2020 - OSF Academy",
            "2019 - Odessa National Polytechnic University, IT-school training course “Front-end development. JavaScript”",
            "2010-2015 - National University “Odessa law academy”"
          ]
        },
        {
          heading: "Experience",
          data: [
            "07.2019 - 09.2019 Part-time junior front-end developer at AVE Startups",
            "09.2018 - 05.2019 Part-time account management at Chudovo IT company",
            "02.2016 - 09.2018 Sales/account manager at AB Soft"
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
