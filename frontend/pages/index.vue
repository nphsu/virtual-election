<template>
  <a-scene>
    <a-assets>
      <img id="floor" :src="floorImg">
    </a-assets>
    <a-sky color="#6e6eff"></a-sky>
    <a-plane
      src="#floor"
      rotation="-90 0 0"
      scale="10000 10000 1"
      repeat="1000 1000"
      shadow="receive: true"
    ></a-plane>
    <a-box color="#658568" width="2" height="2" depth="1"></a-box>
  </a-scene>
</template>

<script>
import 'aframe'
import FloorImg from '~/assets/img/floor-1024.jpg'

export default {
  components: {},
  data() {
    return {
      floorImg: FloorImg
    }
  }
}
</script>
