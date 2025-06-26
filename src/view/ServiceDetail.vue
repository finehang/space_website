<template>
  <div id="ServiceDetail">
    <div class="banner container-fuild text-center">相關服務</div>
    <div class="container">
      <div class="row">
        <div class="col-xs-12 col-sm-12 col-md-3" id="myScrollspy">
          <ul class="nav nav-tabs nav-stacked center-block" id="myNav">
            <p>特色服務</p>
            <li
              :class="item.id == id ? 'active' : ''"
              v-for="(item, index) in serviceNavList"
              :key="index"
            >
              <a href="javascript:;" @click.stop="toSection(item.id)">{{
                item.title
              }}</a>
            </li>
          </ul>
        </div>
        <div class="col-xs-12 col-sm-12 col-md-9 content wow zoomIn">
          <div
            class="content-block"
            v-for="(item, index) in serviceContentList"
            :key="index"
          >
            <h2 :id="item.id">
              {{ item.title }}
              <small>/ {{ item.eng_title }}</small>
            </h2>
            <div v-html="item.content"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup name="serviceDetail">
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'
import WOW from 'wow.js'
const id = ref('section-1')
const serviceNavList = [
  {
    id: 'section-1',
    title: '優化運營服務'
  },
  {
    id: 'section-2',
    title: '效果營銷服務'
  },
  {
    id: 'section-3',
    title: '創意素材支援'
  },
  {
    id: 'section-4',
    title: '運營培訓服務'
  }
]
const serviceContentList = [
  {
    id: 'section-1',
    title: '優化運營服務',
    eng_title: 'Optimize Operation',
    content:
      '我們設有專業的投放運營優化團隊，優化Leader深耕RPG、SLG、小說客戶類型，擁有10年以上甲方優化運營經驗，可針對遊戲客戶不同生命週期定製差異化的推廣方案和針對性的優化培訓課程，從AEO/VO最佳實踐到產品前期預註冊到再行銷，目前已成功幫助數百名客戶實現從0-1，從1-100的增長。'
  },
  {
    id: 'section-2',
    title: '效果營銷服務',
    eng_title: 'Effect Marketing',
    content:
    '我們設有專業的效果行銷優化團隊，優化Leader深耕Casino、Casual、工具客戶類型，擁有8年以上乙方優化推廣經驗，對海外市場素材的精準把控能力以及商業化變現的精準思維，可説明輕度遊戲&工具客戶實現高價值的使用者增量，目前已成功幫助數百名客戶實現量級和效果的增長。'
  },
  {
    id: 'section-3',
    title: '創意素材支援',
    eng_title: 'Creative Support',
    content:
      '服務過超千款出海遊戲產品，擁有豐富的遊戲買量經驗和龐大的素材資源庫支援。 為遊戲客戶提供UE4引擎動畫、真人劇情拍攝、外語配音和特效包裝等專業的創意製作服務，滿足客戶定製化的需求，為遊戲帶來源源不斷的新玩家流量。'
  },
  {
    id: 'section-4',
    title: '運營培訓服務',
    eng_title: 'Operating Training',
    content:
      '專業的運營團隊，將為客戶提供專業以及高效的服務作為核心使命。 針對AAA，iOS 14等Facebook產品更新推廣使用方面進行定期學習，且為客戶提供專業諮詢培訓; 同時也為客戶提供增量建議及方向性溝通，客戶粘性強且排他性高。 以技術為磚，服務建橋，搭建了與客戶溝通的穩健橋樑。'
  }
]
function toSection(_id) {
  id.value = _id
  let top = document.getElementById(id.value).offsetTop
  $(window).scrollTop(top + 300)
  $('#myNav').affix({
    offset: {
      top: 300
    }
  })
}
const route = useRoute()
const props = defineProps({
  id: {
    type: String,
    required: true
    // default: 'section-1222'
  }
})
onMounted(() => {
  console.log('route：', route, route.params, route.query)
  console.log('history.state：', history.state)
  id.value = history.state.id
  console.log(id.value, 'pp')
  let top = document.getElementById(id.value).offsetTop
  $(window).scrollTop(top + 300)
  $('#myNav').affix({
    offset: {
      top: 300
    }
  })
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
  background-image: url('../assets/img/banner_2.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: scroll;
  background-position: center center;
}
ul.nav-tabs {
  width: 200px;
  margin-top: 40px;
  border-radius: 4px;
  background: #fff;
  z-index: 99999;
  border: 1px solid #474747;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.067);
}
ul.nav-tabs li {
  text-align: center;
  margin: 0;
  border-top: 1px solid #474747;
}
ul.nav-tabs p {
  color: #fff;
  font-size: 18px;
  font-weight: bold;
  text-align: center;
  background: #474747;
  margin: 0;
  padding: 10px 0;
}
ul.nav-tabs li:first-child {
  border-top: none;
}
ul.nav-tabs li a {
  margin: 0;
  padding: 8px 16px;
  border-radius: 0;
}
ul.nav-tabs li.active a,
ul.nav-tabs li.active a:hover {
  color: #fff;
  background: #474747;
  border: 1px solid #474747;
}
ul.nav-tabs li:first-child a {
  border-radius: 4px 4px 0 0;
}
ul.nav-tabs li:last-child a {
  border-radius: 0 0 4px 4px;
}
ul.nav-tabs.affix {
  top: 30px;
}
.content-block {
  margin: 50px 0;
}
.content-block > h2 {
  padding: 20px 0;
  border-bottom: 1px solid #ccc;
}
</style>
