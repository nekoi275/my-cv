<template>
  <section id="projects">
    <div class="wrapper">
      <space-invaders v-show="isDesktop()" />
      <sudoku></sudoku>
      <div class="project">
        <a href="https://nekoi275.github.io/aframe-test/" target="_blank" class="project-block">
          <img class="projects-img" src="../assets/project_1.webp" alt="project screenshot">
          Web VR website based on Aframe framework.
        </a>
      </div>
      <div class="project">
        <a href="https://nekoi275.github.io/nice-shop-layout/#" target="_blank" class="project-block">
          <img class="projects-img" src="../assets/project_2.webp" alt="project screenshot">
          Ecommerce website layout sample.
        </a>
      </div>
      <div class="project">
        <a href="https://wardrobe.pages.dev/clothes" target="_blank" class="project-block">
          <img class="projects-img" src="../assets/project_3.webp" alt="project screenshot">
          Personal wardrobe manager app on Vue 3 (Composition API). Test user: test / test12345.
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
  padding-bottom: 50px;
}

.wrapper {
  display: grid;
  grid-gap: 30px;
  grid-template-columns: 600px 600px;
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
