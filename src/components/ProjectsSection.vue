<template>
  <section id="projects">
    <div class="wrapper">
      <space-invaders v-show="isDesktop()" />
      <sudoku></sudoku>
      <a href="http://ave-startups.com/" target="_blank">
        <div class="projects-row">
          <div class="projects-col">
            <img class="projects-img" src="../assets/project_4.png">
            <div class="projects-col-text">
              <p>AVE Startups website.</p>
            </div>
          </div>
        </div>
      </a>
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

  .wrapper {
    display: block;
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
