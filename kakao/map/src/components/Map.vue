<template>
  <div id="Map">
    <h1>{{msg}}</h1>
    <div id="container">
      <div id="dmap"></div>
    </div>
  </div>
</template>
<script
      type="text/javascript"
      src="//dapi.kakao.com/v2/maps/sdk.js?appkey=b199d31d68f1934a33c9bf1ab864e840"
    ></script>
<script>
export default {
  name: "Map",
  data() {
    return {
      msg: "다음맵 테스트"
    };
  },
  mounted() {
    var container = document.getElementById("dmap");
    var options = {
      center: new kakao.maps.LatLng(33.450701, 126.570667),
      level: 3
    };
    var map = new kakao.maps.Map(container, options);

    // geolocation
    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(function(position) {
        var lat = position.coords.latitude,
          lon = position.coords.longitude;

        var locPosition = new kakao.maps.LatLng(lat, lon),
          message = '<div style="padding:5px;">여기에 계신가요?!</div>';

        displayMarker(locPosition, message);
      });
    } else {
      var locPosition = new kakao.maps.LatLng(33.450701, 126.570667),
        message = "geolocation을 사용할 수 없어요.";

      displayMarker(locPosition, message);
    }

    function displayMarker(locPosition, message) {
      var marker = new kakao.maps.Marker({
        map: map,
        position: locPosition
      });

      var iwContent = message,
        iwRemoveable = true;

      // 인포윈도우를 생성합니다
      var infowindow = new kakao.maps.InfoWindow({
        content: iwContent,
        removable: iwRemoveable
      });

      // 인포윈도우를 마커위에 표시합니다
      infowindow.open(map, marker);

      // 지도 중심좌표를 접속위치로 변경합니다
      map.setCenter(locPosition);
    }
  }
};
</script>

<style>
#dmap {
  width: 500px;
  height: 400px;
  display: block;
  margin: 0px auto;
}
</style>