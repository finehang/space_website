<template>
  <div id="ServiceDetail">
    <div class="banner container-fuild text-center">相关服务</div>
    <div class="container">
      <div class="row">
        <div class="col-xs-12 col-sm-12 col-md-3" id="myScrollspy">
          <ul class="nav nav-tabs nav-stacked center-block" id="myNav">
            <p>特色服务</p>
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
    title: '优化运营服务'
  },
  {
    id: 'section-2',
    title: '效果营销服务'
  },
  {
    id: 'section-3',
    title: '创意素材支持'
  },
  {
    id: 'section-4',
    title: '运营培训服务'
  }
]
const serviceContentList = [
  {
    id: 'section-1',
    title: '优化运营服务',
    eng_title: 'Optimize Operation',
    content:
      '我们设有专业的投放运营优化团队，优化Leader深耕RPG、SLG、小说客户类型，拥有10年以上甲方优化运营经验，可针对游戏客户不同生命周期定制差异化的推广方案和针对性的优化培训课程，从AEO/VO最佳实践到产品前期预注册到再营销，目前已成功帮助数百名客户实现从0-1，从1-100的增长。'
  },
  {
    id: 'section-2',
    title: '效果营销服务',
    eng_title: 'Effect Marketing',
    content:
    '我们设有专业的效果营销优化团队，优化Leader深耕Casino、Casual、工具客户类型，拥有8年以上乙方优化推广经验，对海外市场素材的精准把控能力以及商业化变现的精准思维，可帮助轻度游戏&工具客户实现高价值的用户增量，目前已成功帮助数百名客户实现量级和效果的增长。'
  },
  {
    id: 'section-3',
    title: '创意素材支持',
    eng_title: 'Creative Support',
    content:
      '服务过超千款出海游戏产品，拥有丰富的游戏买量经验和庞大的素材资源库支持。为游戏客户提供UE4引擎动画、真人剧情拍摄、外语配音和特效包装等专业的创意制作服务，满足客户定制化的需求，为游戏带来源源不断的新玩家流量。'
  },
  {
    id: 'section-4',
    title: '运营培训服务',
    eng_title: 'Operating Training',
    content:
      '专业的运营团队，将为客户提供专业以及高效的服务作为核心使命。针对AAA，iOS 14等Facebook产品更新推广使用方面进行定期学习，且为客户提供专业咨询培训；同时也为客户提供增量建议及方向性沟通，客户粘性强且排他性高。以技术为砖，服务建桥，搭建了与客户沟通的稳健桥梁。'
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
