<template>
  <section>
    <space-invaders />
    <a href="/clothes/#clothes" target="_blank">
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
    <a href="/osf" target="_blank">
      <div class="projects-row">
        <div class="projects-col">
          <img class="projects-img" src="../assets/project_2.png">
        </div>
        <div class="projects-col-text">
          <p>OSF Academy front end development training project. Basic e-commerce website with an ability to load
            products from JSON and adding to cart and wishlist.</p>
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
    </a>
    <a href="http://ave-startups.com/" target="_blank">
      <div class="projects-row">
        <div class="projects-col">
          <img class="projects-img" src="../assets/project_4.png">
        </div>
        <div class="projects-col-text">
          <p>AVE Startups commercial website.</p>
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
  padding: 150px 0px 0px 30px;
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
.projects-col-text {
  color: var(--main-bg-color);
}
a {
  text-decoration: none;
  height: 100%;
  margin: 30px;
}
</style>
