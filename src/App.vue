<template>
  <div id="app">
    <header-component/>
    <about-me-section/>
  </div>
</template>

<script>
import AboutMeSection from './components/AboutMeSection.vue';
import HeaderComponent from './components/HeaderComponent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    AboutMeSection
  }
}
</script>

<style>
:root {
  --main-bg-color: #dae2e2;
  --header-bg-color: #98a565;
  --dark-font-color: #402e37;
  --light-font-color: #665a6a;
  --second-main-color: #414d08;
}
body {
  font-family: monospace;
  background-color: var(--main-bg-color);
  font-size: 16px;
}
body, div, ul, li, a, h3, h1, h2, h4, h5 {
  margin: 0px;
  padding: 0px;
}
ul {
  list-style-type: none;
}
</style>
