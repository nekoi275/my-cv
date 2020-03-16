<template>
  <div class="game-container">
    <canvas id="game-screen"></canvas>
    <button v-show="buttonShown" @click="start()">Play</button>
  </div>
</template>

<script>
import spriteImage from "../assets/sprite.png";

export default {
  name: "SpaceInvaders",
  data: function() {
    return {
      buttonShown: true,
      isGameOver: false,
      canvasCtx: null,
      spriteFrame: 0,
      alienSprites: [
        [
          {
            x: 0,
            y: 0,
            width: 22,
            height: 16
          },
          {
            x: 0,
            y: 16,
            width: 22,
            height: 16
          }
        ],
        [
          {
            x: 22,
            y: 0,
            width: 16,
            height: 16
          },
          {
            x: 22,
            y: 16,
            width: 16,
            height: 16
          }
        ],
        [
          {
            x: 38,
            y: 0,
            width: 24,
            height: 16
          },
          {
            x: 38,
            y: 16,
            width: 24,
            height: 16
          }
        ]
      ],
      tankSprite: {
        x: 62,
        y: 0,
        width: 22,
        height: 16
      }
    };
  },
  methods: {
    start: function() {
      this.buttonShown = false;
      this.drawSprites();
    },
    drawSprites: function() {
      var img = document.createElement("img");
      img.src = spriteImage;
      img.addEventListener("load", () => {
        let tankXpos = (this.canvasCtx.canvas.width - this.tankSprite.width) / 2;
        let tankYpos = this.canvasCtx.canvas.height - (30 + this.tankSprite.height);
        this.drawSprite(img, this.tankSprite, tankXpos, tankYpos);
      });
    },
    drawSprite: function(img, sprite, x, y) {
      this.canvasCtx.drawImage(
        img,
        sprite.x,
        sprite.y,
        sprite.width,
        sprite.height,
        x,
        y,
        sprite.width,
        sprite.height
      );
    }
  },
  mounted: function() {
    var canvas = document.getElementById("game-screen");
    var ctx = canvas.getContext("2d");
    ctx.canvas.width = 300;
    ctx.canvas.height = 400;
    this.canvasCtx = ctx;
  }
};
</script>

<style scoped>
.game-container {
  position: relative;
  width: 300px;
}
canvas {
  background-color: #000000;
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
