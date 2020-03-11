<template>
  <div id="app">
    <header-component/>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent
  }
}
</script>

<style>
:root {
  --main-bg-color: #dae2e2;
  --header-bg-color: #98a565;
  --dark-font-color: #402e37;
  --light-font-color: #665a6a;
}
body {
  font-family: sans-serif;
  background-color: var(--main-bg-color);
}
body, div, ul, li, a {
  margin: 0px;
  padding: 0px;
}
</style>
