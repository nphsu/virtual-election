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
    <a-camera>
      <a-entity cursor position="0 0 -1"
      geometry="primitive: sphere; radius: 0.005"
      material="color: #000000; shader: flat; opacity: 0.5">

      </a-entity>
    </a-camera>

    <!-- Yellow Box -->
    <a-box
      color="#FFEB3B"
      scale="0.5 0.5 0.5"
      position="-1 1 0"
      animation="property: rotation; to: 0 360 0; loop: true; dur: 5000; easing: linear"
      shadow="cast: true"
    ></a-box>

    <!-- Orange Box -->
    <a-box
      id="orange-box"
      color="#FF5722"
      scale="0.5 0.5 0.5"
      position="1 1 0"
      animation="property: rotation; to: 0 360 0; loop: true; dur: 5000; easing:linear"
      animation__2="property: position; to: 1 1 -2; loop: true; dir: alternate; dur: 5000"
      shadow="cast: true"
    ></a-box>

    <!-- Customn Light | Ambient -->
    <a-entity light="type: ambient; intensity: 0.2"></a-entity>
    <!-- Customn Light | Point -->
    <a-entity
      light="type: point; intensity: 0.8; distance: 10; castShadow: true"
      position="0 2 1.5"
    ></a-entity>
    <!-- Customn Light | Spot -->
    <a-entity
      light="type: spot; target: #orange-box; color: #2E2EFE; angle: 30; penumbra: 0.1; castShadow: true"
      position="0 3 1"
    ></a-entity>
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
