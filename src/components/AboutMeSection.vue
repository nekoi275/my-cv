<template>
  <section id="about">
    <img class="bg-image" src="../assets/top-section-photo.jpg" />
    <ul>
      <li>Name: Drozdova Valeria</li>
      <li>Nickname: Nekoi</li>
      <li>Birthday: 04.01.1993</li>
      <li>Age: 27</li>
      <li>
        <a href="https://github.com/Nekoi275" target="_blank">Github</a>
      </li>
      <li>
        <a href="https://www.instagram.com/valery_nekoi/" target="_blank">Instagram</a>
      </li>
      <li><a href="mailto:nekoi275@gmail.com">E-mail me</a></li>
    </ul>
    <div class="mouse"></div>
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
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
}
.bg-image {
  height: 100vh;
  opacity: 0.5;
  width: 65%;
}
ul,
li,
a {
  color: var(--main-bg-color);
}
ul {
  width: 30%;
  padding: 20px;
  line-height: 40px;
}
.mouse {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  bottom: 30px;
  width: 22px;
  height: 36px;
  border-radius: 25px;
  box-shadow: inset 0 0 0 2px var(--header-bg-color);
}
.mouse::before {
  content: "";
  position: absolute;
  width: 2px;
  height: 8px;
  background-color: var(--header-bg-color);
  left: 10px;
  top: 7px;
  animation: 1.6s ease infinite wheel-up-down;
}
@keyframes wheel-up-down {
  0% {
    transform: translateY(2px);
    opacity: 0;
  }
  30% {
    opacity: 1;
  }
  100% {
    transform: translateY(5px);
    opacity: 0;
  }
}
@media (max-width: 845px) {
  section {
    height: 100%;
    padding-top: 100px;
  }
  .bg-image {
    width: 100%;
    height: auto;
  }
  ul {
    width: 100%;
  }
  .mouse {
    display: none;
  }
}
</style>
