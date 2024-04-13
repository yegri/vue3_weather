<template>
  <div id="mapContainer">
    <div id="map">dd</div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  mounted() {
    if (window.kakao && window.kakao.maps) {
      this.initMap();
    } else {
      const script = document.createElement("script");
      /* global kakao */
      script.onload = () => kakao.maps.load(this.initMap);
      script.src =
        "http://dapi.kakao.com/v2/maps/sdk.js?autoload=false&appkey=e6fd116146d988a99d5ab73ca324765c";
      document.head.appendChild(script);
    }
  },

  methods: {
    initMap() {
      var mapContainer = document.getElementById("map"), // 지도를 표시할 div
        mapOption = {
          center: new kakao.maps.LatLng(36.73035, 127.967487), // 지도의 중심좌표
          level: 13, // 지도의 확대 레벨
        };

      var map = new kakao.maps.Map(mapContainer, mapOption);
      var positions = [
        {
          latlng: new kakao.maps.LatLng(37.5688, 127.967487),
        },
      ];

      // 마커를 생성합니다.
      positions.forEach(function (pos) {
        var marker = new kakao.maps.Marker({
          position: pos.latlng, // 마커의 위치
        });

        // 마커가 지도에 표시되도록 설정
        marker.setMap(map);
      });
    },
  },
};
</script>

<style lang="scss" scoped>
@import "~/scss/main.scss";

#mapContainer {
  @include center;
  width: 100%;
  height: 35%;

  #map {
    width: 80%;
    height: 90%;
    border-radius: 10px;
  }
}
</style>
