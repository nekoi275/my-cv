<template>
  <section id="projects">
    <div class="wrapper">
      <space-invaders v-show="isDesktop()" />
      <sudoku></sudoku>
      <div class="project">
        <a href="http://ave-startups.com/" target="_blank" class="project-block">
          <img class="projects-img" src="../assets/project_4.png">
          <p>AVE Startups website.</p>
        </a>
      </div>
      <div class="project">
        <a href="https://nekoi275.github.io/aframe-test/" target="_blank" class="project-block">
          <img class="projects-img" src="../assets/project_1.png">
          <p>Web VR website based on <a href="https://aframe.io/" target="_blank">A-Frame</a> framework.</p>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import SpaceInvaders from "./SpaceInvadersComponent";
import Sudoku from "./SudokuSolverComponent";

export default {
  name: 'ProjectsSection',
  components: {
    SpaceInvaders,
    Sudoku
  },
  methods: {
    isDesktop: function () {
      return window.innerWidth >= 1000;
    }
  }
};
</script>

<style scoped>
section {
  background-color: var(--dark-font-color);
  padding-top: 130px;
}

.wrapper {
  display: grid;
  grid-gap: 30px;
  grid-template-columns: 600px 600px;
  grid-auto-rows: 520px;
  justify-content: center;
}

.project {
  width: 530px;
}

.project-block {
  padding: 10px;
  border: 2px solid var(--light-font-color);
  color: var(--main-bg-color);
  display: block;
  text-align: center;
}

.project-block:hover {
  border: 2px solid var(--second-main-color);
}

.projects-img {
  width: 500px;
  height: auto;
}

@media (max-width: 845px) {
  section {
    padding-top: 100px;
  }

  .wrapper {
    display: block;
  }

  .projects-img {
    width: 300px;
    height: auto;
  }

  .project {
    width: 360px;
    margin: auto;
    margin-bottom: 10px;
  }
}
</style>
