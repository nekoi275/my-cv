<template>
  <section>
      <img class="bg-image" src="../assets/top-section-photo.jpg">
      <ul>
          <li>Name: Drozdova Valeria</li>
          <li>Nickname: Nekoi</li>
          <li>Birthday: 04.01.1993</li>
          <li>Age: 27</li>
          <li><a href="https://github.com/Nekoi275">Github</a></li>
          <li><a href="https://www.instagram.com/valery_nekoi/">Instagram</a></li>
      </ul>
  </section>
</template>

<script>
export default {
  name: "AboutMeSection"
};
</script>

<style scoped>
section {
    background-color: var(--dark-font-color);
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.bg-image {
    height: 100vh;
    opacity: 0.5;
    flex: 50%;
}
ul, li, a {
    color: var(--main-bg-color);
}
ul {
    flex: 50%;
    padding: 20px;
    line-height: 40px;
}
</style>
