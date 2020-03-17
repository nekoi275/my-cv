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
      config: {
        aliens: {
          sprites: [
            [
              {
                x: 0,
                y: 0,
                width: 22,
                height: 16,
                margin: 0
              },
              {
                x: 0,
                y: 16,
                width: 22,
                height: 16,
                margin: 0
              }
            ],
            [
              {
                x: 22,
                y: 0,
                width: 16,
                height: 16,
                margin: 4
              },
              {
                x: 22,
                y: 16,
                width: 16,
                height: 16,
                margin: 4
              }
            ],
            [
              {
                x: 38,
                y: 0,
                width: 24,
                height: 16,
                margin: 0
              },
              {
                x: 38,
                y: 16,
                width: 24,
                height: 16,
                margin: 0
              }
            ]
          ],
          rows: 5,
          columns: 10,
          types: [1, 0, 0, 2, 2]
        },
        tank: {
          sprite: {
            x: 62,
            y: 0,
            width: 22,
            height: 16
          },
          xOffset: 0
        }
      },
      aliens: []
    };
  },
  methods: {
    start: function() {
      this.buttonShown = false;
      this.init();
      this.render();
    },
    render: function() {
      var img = document.createElement("img");
      img.src = spriteImage;
      img.addEventListener("load", () => {
        let tankXPos =
          (this.canvasCtx.canvas.width - this.config.tank.sprite.width) / 2;
        let tankYPos =
          this.canvasCtx.canvas.height - (30 + this.config.tank.sprite.height);
        this.drawSprite(img, this.config.tank.sprite, tankXPos, tankYPos);
        for (let i = 0; i < this.aliens.length; i++) {
          let alien = this.aliens[i];
          this.drawSprite(img, alien.sprite[this.spriteFrame], alien.x, alien.y);
        }
      });
    },
    init: function() {
      const padding = 30;

      for (let rowIndex = 0; rowIndex < this.config.aliens.rows; rowIndex++) {
        for (
          let colIndex = 0;
          colIndex < this.config.aliens.columns;
          colIndex++
        ) {
          let typeNumber = this.config.aliens.types[rowIndex];
          let sprite = this.config.aliens.sprites[typeNumber];
          this.aliens.push({
            sprite: sprite,
            x: padding + colIndex * padding + sprite[0].margin,
            y: padding + rowIndex * padding,
            w: sprite[0].width,
            h: sprite[0].height
          });
        }
      }
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
    ctx.canvas.width = 600;
    ctx.canvas.height = 500;
    this.canvasCtx = ctx;
  }
};
</script>

<style scoped>
.game-container {
  position: relative;
  width: 600px;
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
