<template>
  <div id="CompanyIntroduction">
    <div class="banner container-fuild text-center">关于我们</div>
    <div class="container">
      <div class="row CompanyIntroduction-container">
        <div class="col-xs-12 col-sm-12 col-md-6 wow zoomIn">
          <img
            class="img-responsive center-block"
            src="@/assets/img/about_img.png"
            alt="about"
          />
        </div>
        <div class="col-xs-12 col-sm-12 col-md-6">
          <h3>香港构想空间网络科技有限公司</h3>
          <p class=".text-justify">
            我们是一家专业为游戏、工具、泛娱乐等移动行业提供精准出海营销的服务商。创始人来自PayPal、香港品众、猎豹等一线出海企业。2019年1月起正式成为 Facebook顶级代理商，同时加入Google优秀合作伙伴（Google Premier Partner）。业务遍布北 京、上海、广州、深圳、长沙、重庆、成都、武汉、合肥等 30 余个城市。
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup name="CompanyIntroduction">
import WOW from 'wow.js'
import { onMounted } from 'vue'
onMounted(() => {
  let wow = new WOW()
  wow.init()
})
</script>

<style scoped>
.banner {
  color: #fff;
  font-size: 30px;
  height: 150px;
  line-height: 150px;
  background-image: url('../assets/img/banner1.png');
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: scroll;
  background-position: center center;
}
.row {
  margin-right: 0;
  margin-left: 0;
}
.CompanyIntroduction-container {
  padding: 100px 0;
  color: #808080;
  transition: all ease 0.5s;
}
.CompanyIntroduction-container > div > p {
  font-size: 14px;
  line-height: 2.5rem;
}
@media screen and (max-width: 997px) {
  .CompanyIntroduction-container {
    padding: 10px 0;
    color: #808080;
  }
}
</style>
