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
        <li><button @click="changeTheme()">Change theme</button></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'HeaderComponent',
  data: function () {
    return {
      colorSchemeNum: 0,
      colorSchemes: [{
        mainBg: '#dae2e2',
        headerBg: '#98a565',
        darkFont: '#402e37',
        lightFont: '#665a6a',
        secondMain: '#414d08'
      }, {
        mainBg: '#DDE2DC',
        headerBg: '#C5998C',
        darkFont: '#4E4035',
        lightFont: '#A4C392',
        secondMain: '#D67F54'
      }],
      colorNames: {
        mainBg: '--main-bg-color',
        headerBg: '--header-bg-color',
        darkFont: '--dark-font-color',
        lightFont: '--light-font-color',
        secondMain: '--second-main-color'
      }
    }
  },
  methods: {
    scrollTo: function (id) {
      document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
    },
    changeTheme: function () {
      this.colorSchemeNum >= this.colorSchemes.length - 1 ? this.colorSchemeNum = 0 : this.colorSchemeNum++;
      for (const key in this.colorNames) {
        document.querySelector(':root').style.setProperty(this.colorNames[key], this.colorSchemes[this.colorSchemeNum][key])
      }
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
}

li:hover {
  color: var(--dark-font-color);
}

.logo {
  max-width: 135px;
  cursor: pointer;
}

.logo-text {
  font-size: 35px;
  color: var(--main-bg-color);
  background-image: linear-gradient(92deg, var(--dark-font-color), var(--second-main-color));
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

button {
  border: none;
  background-color: var(--light-font-color);
  color: var(--dark-font-color);
  padding: 10px;
  border-radius: 20px;
  cursor: pointer;
  letter-spacing: 2px;
  text-align: center;
}

button:hover {
  color: var(--light-font-color);
  background-color: var(--dark-font-color);
}

@media (max-width: 845px) {
  li {
    display: block;
    margin-bottom: 5px;
    text-align: center;
  }
}
</style>
