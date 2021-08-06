<template>
  <div>
      <div id="cesiumContainer">
      </div>
      <div>
        <router-link to="/HelloWorld">turn</router-link>
        <router-link to="/test">turn2</router-link>
      </div>
      <router-view></router-view>
  </div>
</template>
 
<script>
let Cesium = require("cesium/Cesium")
import 'cesium/Widgets/widgets.css'
// 导出组件
export default {
  name: "cesiumContainer",
  mounted () {
    let config = {
        geocoder: false,   // 位置查找工具
        homeButton: false,  // 视角返回初始位置
        sceneModePicker: false,   // 选择视角的模式（球体、平铺、斜视平铺）
        baseLayerPicker: false,    // 图层选择器（地形影像服务）
        navigationHelpButton: false,   // 导航帮助(手势，鼠标)
        animation: false,   // 左下角仪表盘（动画器件）
        timeline: false,   // 底部时间线
        fullscreenButton: false,   // 全屏
        vrButton: false,  // VR
      }
    var viewer = new Cesium.Viewer("cesiumContainer",config);
    viewer._cesiumWidget._creditContainer.style.display = "none";
  },
 
};
</script>
 
<style scoped>
 
#cesiumContainer {
  width: 100%;
  height: 100%;
}
 
</style>

