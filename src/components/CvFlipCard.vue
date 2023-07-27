<template>
  <div class="flip-card">
    <div class="flip-card-inner">
      <div class="flip-card-front">
        <h3>{{ cardInfo.heading }}</h3>
      </div>
      <div class="flip-card-back">
        <ul v-for="cardInfoData in cardInfo.data" :key="cardInfoData.id">
          <li>{{ cardInfoData }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CvFlipCard',
  props: {
    cardInfo: Object
  }
};
</script>

<style scoped>
.flip-card {
  background-color: transparent;
  width: 300px;
  height: 300px;
  perspective: 1000px;
}
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}
.flip-card-front,
.flip-card-back {
  position: absolute;
  padding: 20px;
  box-sizing: border-box;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
}
.flip-card-front {
  background-color: var(--second-main-color);
  color: var(--main-bg-color);
  text-align: center;
}
.flip-card-back {
  background-color: var(--dark-font-color);
  color: var(--main-bg-color);
  transform: rotateY(180deg);
  text-align: left;
}
li {
    padding: 10px;
}
</style>