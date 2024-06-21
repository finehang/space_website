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
            我们是一家出海全球化营销服务商，通过数字营销和社交媒体广告代理服务，致力于为跨境出海企业提供一站式解决方案。业务涵盖了社交媒体管理、内容创意营销、数据分析、MEDIABUY等多个领域。公司以效果营销为导向和精细化运营为核心，致力于游戏应用电商等多品类的全球化推广服务 ，打造品牌与产品出海。通过精准的数据分析和创新的营销策略，助力企业全球数字化营销增长。
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
