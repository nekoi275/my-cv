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
      spriteImage: null,
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
          types: [1, 0, 0, 2, 2],
          bulletColor: "#ffff00",
          shootProbability: 0.03,
          bulletSpeed: 4
        },
        tank: {
          sprite: {
            x: 62,
            y: 0,
            width: 22,
            height: 16
          },
          xPos: 0,
          yPos: 0,
          bulletColor: "#ff0000",
          bulletSpeed: -8,
          speed: 4
        },
        bullet: {
          width: 2,
          height: 6
        },
        screenPadding: 30
      },
      control: {
        right: false,
        left: false,
        fire: false
      },
      aliens: [],
      bullets: []
    };
  },
  methods: {
    start: function() {
      this.buttonShown = false;
      this.init();
    },
    render: function() {
      this.canvasCtx.clearRect(
        0,
        0,
        this.canvasCtx.canvas.width,
        this.canvasCtx.canvas.height
      );

      this.drawSprite(
        this.config.tank.sprite,
        this.config.tank.xPos,
        this.config.tank.yPos
      );
      for (let i = 0; i < this.aliens.length; i++) {
        let alien = this.aliens[i];
        this.drawSprite(alien.sprite[this.spriteFrame], alien.x, alien.y);
      }
      for (let i = 0; i < this.bullets.length; i++) {
        let bullet = this.bullets[i];
        this.canvasCtx.fillStyle = bullet.color;
        this.canvasCtx.fillRect(bullet.x, bullet.y, bullet.w, bullet.h);
      }
    },
    init: function() {
      this.initState();
      this.initControl();
      this.initSpriteImage(this.run);
    },
    initState: function() {
      this.config.tank.xPos =
        (this.canvasCtx.canvas.width - this.config.tank.sprite.width) / 2;
      this.config.tank.yPos =
        this.canvasCtx.canvas.height - (30 + this.config.tank.sprite.height);

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
            x:
              this.config.screenPadding +
              colIndex * this.config.screenPadding +
              sprite[0].margin,
            y: this.config.screenPadding + rowIndex * this.config.screenPadding,
            w: sprite[0].width,
            h: sprite[0].height
          });
        }
      }
    },
    initSpriteImage: function(afterInit) {
      this.spriteImage = document.createElement("img");
      this.spriteImage.src = spriteImage;
      this.spriteImage.addEventListener("load", afterInit);
    },
    initControl: function() {
      document.addEventListener("keydown", event => {
        this.control.left = event.keyCode == 37;
        this.control.right = event.keyCode == 39;
      });
      document.addEventListener("keyup", () => {
        this.control.left = false;
        this.control.right = false;
        this.control.fire = event.keyCode == 32;
      });
    },
    drawSprite: function(sprite, x, y) {
      this.canvasCtx.drawImage(
        this.spriteImage,
        sprite.x,
        sprite.y,
        sprite.width,
        sprite.height,
        x,
        y,
        sprite.width,
        sprite.height
      );
    },
    run: function() {
      let loop = () => {
        this.update();
        this.render();
        if (!this.isGameOver) {
          window.requestAnimationFrame(loop);
        }
      };
      window.requestAnimationFrame(loop);
    },
    update: function() {
      this.updateTank();
      this.updateBullets();
      this.updateAliens();
    },
    updateTank: function() {
      if (
        this.control.left &&
        this.config.tank.xPos > this.config.screenPadding
      ) {
        this.config.tank.xPos -= this.config.tank.speed;
      }
      if (
        this.control.right &&
        this.config.tank.xPos <
          this.canvasCtx.canvas.width -
            this.config.screenPadding -
            this.config.tank.sprite.width
      ) {
        this.config.tank.xPos += this.config.tank.speed;
      }
      if (this.control.fire) {
        this.control.fire = false;
        this.bullets.push({
          x: this.config.tank.xPos + this.config.tank.sprite.width / 2,
          y: this.config.tank.yPos,
          speed: this.config.tank.bulletSpeed,
          w: this.config.bullet.width,
          h: this.config.bullet.height,
          color: this.config.tank.bulletColor
        });
      }
    },
    updateBullets: function() {
      let isShooting = Math.random() < this.config.aliens.shootProbability;

      for (let i = 0; i < this.bullets.length; i++) {
        let bullet = this.bullets[i];
        bullet.y += bullet.speed;
        if (
          bullet.y + bullet.height < 0 ||
          bullet.y > this.canvasCtx.canvas.height
        ) {
          this.bullets.splice(i, 1);
          i--;
          continue;
        }
      }

      if (isShooting && this.aliens.length > 0) {
        let randomAlien = this.aliens[
          Math.round(Math.random() * (this.aliens.length - 1))
        ];
        this.bullets.push({
          x: randomAlien.x + randomAlien.w / 2,
          y: randomAlien.y + randomAlien.h,
          speed: this.config.aliens.bulletSpeed,
          w: this.config.bullet.width,
          h: this.config.bullet.height,
          color: this.config.aliens.bulletColor
        });
      }
    },
    updateAliens: function() {

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
