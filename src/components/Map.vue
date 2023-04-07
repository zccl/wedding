<template>
  <div>
    <div class="map-container" ref="gal">
      <div id="container" class="container"></div>
    </div>
    <div class="info-box">
      纬度：{{ form.lat }}
      <br />
      经度：{{ form.lng }}
      <p>详细地址：{{ form.address }}</p>
    </div>
  </div>
</template>

<script>
import AMapLoader from '@amap/amap-jsapi-loader';
window._AMapSecurityConfig = {
  // 安全密钥
  securityJsCode: 'aad284f07aa4ec7af1182a2d1392ee09',
};
export default {
  name: 'TestIndex',
  data() {
    return {
      // 地图实例
      map: null,
      // 标记点
      marker: '',
      // 地址逆解析
      geoCoder: null,
      // 位置信息
      form: {
        lng: 113.752687,
        lat: 31.026694,
        address: '',
        adcode: '', //地区编码
      },
      // 搜索节流阀
      loading: false,
      // 搜索提示信息
      options: [],
    };
  },
  methods: {
    initMap() {
      AMapLoader.load({
        // 你申请的Key
        key: '72531292c6b7b6f883d4cad1771850b5',
        version: '2.0',
        // 需要用到的插件
        plugins: ['AMap.Geocoder'],
      })
        .then((AMap) => {
          this.map = new AMap.Map('container', {
            viewMode: '3D', //是否为3D地图模式
            zoom: 14, //初始化地图级别
            center: [113.752687, 31.026694], //初始化地图中心点位置
          });
          //地址逆解析插件
          this.geoCoder = new AMap.Geocoder({});
          // 搜索提示插件
          //   this.AutoComplete = new AMap.AutoComplete({ city: '全国' });

          // 默认标记地址
          // 清除点
          this.removeMarker();
          // 标记点
          this.setMapMarker(AMap);
        })
        .catch((err) => {
          // 错误
          console.log(err);
        });
    },
    // 标记点
    setMapMarker(AMap) {
      // 自动适应显示想显示的范围区域
      //   this.map.setFitView();
      this.marker = new AMap.Marker({
        map: this.map,
        position: [this.form.lng, this.form.lat],
      });
      // 逆解析地址
      this.toGeoCoder();
      //   this.map.setFitView();
      this.map.add(this.marker);
    },
    // 清除点
    removeMarker() {
      if (this.marker) {
        this.map.remove(this.marker);
      }
    },
    // 逆解析地址
    toGeoCoder() {
      let lnglat = [this.form.lng, this.form.lat];
      this.geoCoder.getAddress(lnglat, (status, result) => {
        if (status === 'complete' && result.regeocode) {
          this.form.address = result.regeocode.formattedAddress;
        }
      });
    },
  },
  mounted() {
    this.initMap();
  },
};
</script>

<style scoped>
.container {
  width: 90%;
  height: 240px;
  margin: 0 auto;
}
.info-box {
  padding: 10px 20px;
  line-height: 1.7;
}
</style>
