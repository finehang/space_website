<template>
  <div id="NewsInformation">
    <div class="container">
      <div class="container text-center">
        <h3>行业动态</h3>
        <p style="color: #b2b2b2">Industry Dynamics</p>
      </div>
      <div class="nav container text-center">
        <a href="javascript:" class="active">行业新闻</a>
      </div>
      <ul class="news-container container-fuild">
        <li v-for="(item, index) in newsList" :key="index" class="wow fadeIn">
          <div class="content">
            <p>{{ item.title }}</p>
            <p>{{ item.introduce }}</p>
          </div>
          <div class="time">
            <p>{{ item.date }}</p>
            <span>{{ item.year }}</span>
          </div>
          <div class="circle">
            <img src="@/assets/img/circle.png" alt="circle"/>
            <i class="line center-block"></i>
          </div>
        </li>
      </ul>
      <div class="contaianer-fuild text-center more">
        <i class="glyphicon glyphicon-th"></i>
      </div>
    </div>
  </div>
</template>

<script setup>
import WOW from 'wow.js'
import { onMounted } from 'vue'
const newsList = [
  {
    id: '001',
    title: '出海先锋茶话会“爆”满收官，畅聊游戏出海走向',
    introduce:
      '2024年4月25日，携手广大大，联合武汉数字创意与游戏产业协会，特邀Meta、Google两大媒体相聚春日武汉，成功举办【听万物生长，话出海新机】主题出海先锋茶话会。',
    date: '04-25',
    year: '2024'
  },
  {
    id: '002',
    title: 'ONE有引力，聚力不凡｜IdeaSpace年会盛典回顾',
    introduce:
      '2023年，对于我们是突破的一年，业务成绩斐然，有目共睹；是温暖的一年，公司周年纪念、活力团建等活动快乐又温馨。我们的伙伴们，沿着公司发展的方向努力拼搏，共同进步。',
    date: '04-02',
    year: '2024'
  }
]
onMounted(() => {
  let wow = new WOW()
  wow.init()
})
</script>

<style scoped>
.nav {
  margin: 20px 0;
}
.nav > a {
  display: inline-block;
  text-decoration: none;
  width: 120px;
  height: 45px;
  line-height: 45px;
  color: #333;
  border: 1px solid #333;
}
.nav > a.active {
  color: #1e73be;
  border-color: #1e73be;
}
.nav > a:hover {
  color: #1e73be;
  border-color: #1e73be;
}
.news-container {
  overflow: hidden;
  margin-bottom: 0;
}
.news-container > li {
  width: 55.6%;
  height: 120px;
  float: left;
  color: #333;
  text-align: right;
  border-left: 1px solid transparent;
  border-right: 1px solid transparent;
}
.news-container > li:hover {
  color: #1e73be;
  border: 1px solid #1e73be;
  cursor: pointer;
}
.news-container > li:nth-of-type(2n) {
  float: right;
  text-align: left;
}
.news-container > li > .content {
  width: 60%;
  float: left;
  padding: 20px 0;
}
.news-container > li > .time {
  width: 20%;
  float: left;
  padding: 10px 0;
}
.news-container > li > .time > p {
  font-size: 30px;
  margin: 5px 0;
}
.news-container > li > .circle {
  width: 20%;
  height: 100%;
  float: left;
  position: relative;
}
.news-container > li > .circle > img {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  margin: auto;
  width: 20px;
  height: 20px;
}
.news-container > li > .circle > i {
  display: block;
  width: 1px;
  height: 100%;
  background: #707070;
}
.news-container > li:nth-of-type(2n) > .content {
  float: right;
}
.news-container > li:nth-of-type(2n) > .time {
  float: right;
}
.news-container > li:nth-of-type(2n) > .circle {
  float: right;
}
.news-container > li:nth-of-type(1) > .circle > i {
  height: 50%;
  position: absolute;
  top: 50%;
  left: 50%;
}
.more {
  font-size: 25px;
  color: #707070;
}
.more > i {
  cursor: pointer;
}
@media screen and (max-width: 767px) {
  .news-container > li {
    width: 100%;
  }
  .news-container > li > .content {
    width: 70%;
    text-align: left;
    float: right;
  }
  .news-container > li > .time {
    width: 30%;
    text-align: left;
    float: right;
  }
  .news-container > li > .circle {
    display: none;
  }
}
</style>
