<template>
  <a-scene>
    <!-- Assets -->
    <a-assets>
      <img id="floor" :src="floorImg">
      <!-- <img id="firefox" src="firefoxImg"> -->
    </a-assets>
    <!-- Sky -->
    <a-sky color="#212121"></a-sky>
    <!-- Ground -->
    <a-plane
      src="#floor"
      rotation="-90 0 0"
      scale="10000 10000 1"
      repeat="1000 1000"
      shadow="receive: true"
    ></a-plane>
    <!-- Camera -->

    <!-- Yellow Box -->
    <a-box
      color="#FFEB3B"
      scale="0.5 0.5 0.5"
      position="-1 1 0"
      animation="property: rotation; to: 0 360 0; loop: true; dur: 5000; easing: linear"
    ></a-box>

    <!-- Orange Box -->
    <a-box
      id="orage-box"
      color="#FF5722"
      scale="0.5 0.5 0.5"
      position="1 1 0"
      animation="property: rotation; to: 0 360 0; loop: true; dur: 5000; easing:linear"
    ></a-box>
  </a-scene>
</template>

<script>
import 'aframe'
import FloorImg from '~/assets/img/floor-1024.jpg'
// import FireFoxImg from '~/assets/img/firefox.png'

export default {
  components: {},
  data() {
    return {
      floorImg: FloorImg
      // fireFoxImg: FireFoxImg
    }
  }
}
</script>
