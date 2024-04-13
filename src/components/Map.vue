<template>
  <div id="mapContainer">
    <div id="map">dd</div>
  </div>
</template>

<script>
export default {
  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
@import "~/scss/main.scss";

#mapContainer {
  @include center;
  width: 100%;
  height: 35%;
  background-color: whitesmoke;

  #map {
    width: 80%;
    height: 90%;
    border-radius: 10px;
  }
}
</style>
