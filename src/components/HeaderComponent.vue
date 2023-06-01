<template>
  <header>
    <div @click="scrollTo('about')" class="logo">
      <h3 class="logo-text">Logo here</h3>
    </div>
    <nav>
      <ul>
        <li @click="scrollTo('about')">About me</li>
        <li @click="scrollTo('cv')">My CV</li>
        <li @click="scrollTo('projects')">Projects</li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
  methods: {
    scrollTo: function(id) {
      document.getElementById(id).scrollIntoView({behavior: "smooth"});
    }
  } 
};
</script>

<style scoped>
header {
  background-color: var(--header-bg-color);
  display: flex;
  padding: 10px;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0px;
  left: 0px;
  right: 0px;
  z-index: 10;
}
li {
  display: inline-block;
  margin: 0px 10px;
  cursor: pointer;
  color: var(--light-font-color);
  font-weight: 900;
  border-bottom: 1px solid var(--light-font-color);
}
li:hover {
  color: var(--dark-font-color);
  border-bottom: 1px solid var(--dark-font-color);
}
.logo {
  max-width: 135px;
  cursor: pointer;
}
.logo-text {
  font-size: 35px;
  color: #dae2e2;
  background-image: linear-gradient(92deg, #402e37, #414d08);
  background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: change-color 5s infinite linear;
}
@keyframes change-color {
  from {
    filter: hue-rotate(0deg);
  }
  to {
    filter: hue-rotate(-360deg);
  }
}
</style>
