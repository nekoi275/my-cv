<template>
  <section id="projects">
    <space-invaders v-show="isDesktop()"/>
<!--     <a href="/clothes/#clothes" target="_blank">
      <div class="projects-row">
        <div class="projects-col">
          <img class="projects-img" src="../assets/project_1.png">
        </div>
        <div class="projects-col-text">
          <p>Personal wadrobe manager. Allows to add/edit/delete info about clothes (photo, year of purchase, color,
            price, etc.), has an ability to keep track of old clothes by moving them to other table. Filters and sorting
            based on given info.</p>
        </div>
      </div>
    </a>
    <a href="/swapi" target="_blank">
      <div class="projects-row">
        <div class="projects-col">
          <img class="projects-img" src="../assets/project_3.png">
        </div>
        <div class="projects-col-text">
          <p>Star Wars Api front end page. Provides information about starships from swapi.com</p>
        </div>
      </div>
    </a> -->
    <a href="http://ave-startups.com/" target="_blank">
      <div class="projects-row">
        <div class="projects-col">
          <img class="projects-img" src="../assets/project_4.png">
        </div>
        <div class="projects-col-text">
          <p>AVE Startups website.</p>
        </div>
      </div>
    </a>
  </section>
</template>

<script>
import SpaceInvaders from "./SpaceInvadersComponent";

export default {
  name: "ProjectsSection",
  components: {
      SpaceInvaders
  },
  methods: {
    isDesktop: function() {
      return window.innerWidth >= 1000;
    }
  }
};
</script>

<style scoped>
section {
  background-color: var(--dark-font-color);
  height: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  padding-top: 150px;
  padding-bottom: 150px;
}
.projects-img {
  width: 500px;
  height: auto;
}
.projects-row {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  box-sizing: border-box;
  max-width: 550px;
  padding: 10px;
  border: 2px solid var(--light-font-color);
}
.projects-row:hover {
  border: 2px solid var(--second-main-color);
}
.projects-col-text {
  color: var(--main-bg-color);
}
a {
  text-decoration: none;
  height: 100%;
  margin: 30px;
}
@media (max-width: 845px) {
  section {
    padding-top: 100px;
  }
  .projects-img {
    width: 300px;
    height: auto;
  }
  a {
    margin: 30px 0px;
  }
}
</style>
