<template>
  <header>
    <nav>
      <ul>
        <li>About me</li>
        <li>My CV</li>
        <li>Projects</li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'HeaderComponent'
}
</script>

<style scoped>
header {
  background-color: var(--header-bg-color);
  display: flex;
  padding: 25px;
  justify-content: space-between;
  position: fixed;
  top: 0px;
  left: 0px;
  right: 0px;
}
ul {
  list-style-type: none;
}
li {
  display: inline-block;
  margin: 0px 10px;
  cursor: pointer;
  color: var(--light-font-color);
}
li:hover {
  color: var(--dark-font-color);
}
</style>
