<template>
  <div id="cesiumContainer"></div>
</template>

<script>
import 'cesium/Build/Cesium/Widgets/widgets.css'
import * as Cesium from 'Cesium'

export default {
  name: 'CesiumContainer',
  mounted() {
    /* eslint no-new: */
    // new Viewer('cesiumContainer')
    const viewer = new Cesium.Viewer('cesiumContainer')
    const entity = viewer.entities.add({
      // 22.5445042387,114.0872077942 bing地图华强北地图poi 经纬度
      //Google map huaqingbei lat and lon 22.5440904825,114.0854052726

      // 深圳市民中心  22.5436850360,114.0596499327
      position: Cesium.Cartesian3.fromDegrees(114.0596499327, 22.543685036),
      model: {
        //uri: '3Dmodels/Cesium_Air.glb'
        //uri: '3Dmodels/models/WoodTower/Wood_Tower.gltf'

        uri: '/model/szsmzx.gltf'
      }
    })
    viewer.trackedEntity = entity
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#cesiumContainer {
  width: 100%;
  height: 100%;
}
</style>
