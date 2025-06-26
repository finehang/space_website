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
          <h3>GATHER WISDOM</h3>
          <p class=".text-justify">
            我們是一家出海全球化營銷服務商，通過數位行銷和社交媒體廣告代理服務，致力於為跨境出海企業提供一站式解決方案。 業務涵蓋了社交媒體管理、內容創意營銷、數據分析、MEDIABUY等多個領域。 公司以效果行銷為導向和精細化運營為核心，致力於遊戲應用電商等多品類的全球化推廣服務 ，打造品牌與產品出海。 通過精準的數據分析和創新的行銷策略，助力企業全球數位化營銷增長。
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
