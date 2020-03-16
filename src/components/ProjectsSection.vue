<template>
  <section>
    <space-invaders/>
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
  height: 100vh;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  padding: 150px 0px 0px 30px;
}
</style>
