<template>
  <section id="projects">
    <space-invaders v-show="isDesktop()"/>
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
    <sudoku></sudoku>
  </section>
</template>

<script>
import SpaceInvaders from "./SpaceInvadersComponent";
import Sudoku from "./SudokuSolverComponent";

export default {
  name: "ProjectsSection",
  components: {
      SpaceInvaders,
      Sudoku
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
  gap: 30px;
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
