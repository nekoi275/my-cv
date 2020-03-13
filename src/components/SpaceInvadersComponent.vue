<template>
  <div class="game-container">
    <canvas id="game-screen"></canvas>
    <button v-show="buttonShown" @click="start()">Play</button>
  </div>
</template>

<script>
export default {
  name: "SpaceInvaders",
  data: function() {
    return {
      buttonShown: true,
      canvasCtx: null
    };
  },
  methods: {
    start: function() {
      this.buttonShown = false;
    }
  },
  mounted: function() {
    var canvas = document.getElementById("game-screen");
    var ctx = canvas.getContext("2d");
    this.canvasCtx = ctx;
  }
};
</script>

<style scoped>
.game-container {
  position: relative;
  width: 500px;
  height: 100vh;
}
canvas {
  background-color: #000000;
  width: 500px;
  height: 100vh;
}
button {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translateX(-50%) translateY(-50%);
  border: none;
  background-color: var(--light-font-color);
  color: var(--dark-font-color);
  padding: 20px;
  border-radius: 20px;
  cursor: pointer;
  font-size: 20px;
  letter-spacing: 4px;
}
button:hover {
  color: var(--light-font-color);
  background-color: var(--dark-font-color);
}
</style>
