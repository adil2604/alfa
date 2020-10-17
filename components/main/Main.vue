<template>
  <content>

    <div class="block-1">
      <div class="slider-block">

        <div class="under-slider">
          <div class="under-slider-block">
            <img src="../../static/under.png" style="width:19%" alt="">
            <img src="../../static/under.png" style="width:19%" alt="">
            <img src="../../static/under.png" style="width:19%" alt="">
            <img src="../../static/under.png" style="width:19%" alt="">
            <img src="../../static/under.png" style="width:19%" alt="">
          </div>
        </div>
      </div>
    </div>

    <div class="container">
      <p style="font-weight: 700;font-size: 24px;">Горячие предложения</p>
      <VmProductsList></VmProductsList>
    </div>

    <div class="news-block block-1">
      <div class="news-header">
        <div class="news-header-item current">Новости компании</div>
        <div class="news-header-item">Новости IT</div>
        <div class="news-header-item">Пресс-релизы</div>
        <div class="news-header-item">Конкурсы</div>
      </div>

      <div class="news-items">
        <div class="news-item">
          <img src="../../static/news.png" alt="">
          <div class="news-item-inside">
            <a href="">В Казахстане обнаружено почти 5000 спамерских ресурсов</a>
            <p>Lorem ipsum, dolor sit amet consectetur, adipisicing elit. Velit voluptates facere, cupiditate tenetur,
              adipisci quod eveniet aliquid eius beatae. Officiis, earum sapiente repellat, in praesentium, est,
              deleniti magni harum dolores quibusdam consequuntur. Facilis nostrum aliquam, voluptatibus veritatis,
              reiciendis ea dolores!</p>
            <span>9 октября</span> <span>12 просмотров</span>
          </div>
        </div>

        <div class="news-item">
          <img src="../../static/news.png" alt="">
          <div class="news-item-inside">
            <a href="">В Казахстане обнаружено почти 5000 спамерских ресурсов</a>
            <p>Lorem ipsum, dolor sit amet consectetur, adipisicing elit. Velit voluptates facere, cupiditate tenetur,
              adipisci quod eveniet aliquid eius beatae. Officiis, earum sapiente repellat, in praesentium, est,
              deleniti magni harum dolores quibusdam consequuntur. Facilis nostrum aliquam, voluptatibus veritatis,
              reiciendis ea dolores!</p>
            <span>9 октября</span> <span>12 просмотров</span>
          </div>
        </div>
      </div>
    </div>


  </content>
</template>

<script>
import VmProductsList from '@/components/products_list/ProductsListContainer'

export default {
  name: "Main",
  components: {VmProductsList}
}
</script>

<style scoped>
html, body {
  margin: 0;
  padding: 0;
}

.block-1 {
  width: 70%;
  margin: 0 auto;
  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
}

.header {
  background: #BC090C;
  color: #fff;
  height: 38px;
  line-height: 38px;
}

.header > .block-1 {
  position: relative;
}

.header a:last-child {
  position: absolute;
  right: 0;
  color: #fff;
}


.header-2 > .block-1 {
  padding: 20px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header-2 {
  height: 100px;
}

.heighter {
  height: 30px;
}

.under-slider-block {
  text-align: center;
}

.under-slider-block img {
  cursor: pointer;
}

.hot {
  position: absolute;
  top: 890px;
  width: 100%;
  height: 189px;
  z-index: -1;
  background: #BC090C;
}

.hot-write * {
  color: #fff;
}

.under-hot .block-1 {
  z-index: 1;
  height: 100px;
  margin-top: 160px;
  padding: 30px;
  background: #fff;
}

.items {
  display: flex;
  justify-content: space-between;
}

.items .item {
  padding: 10px;
  width: 20%;
}

.news-block {
  margin-top: 215px;
}

.news-header {
  background: #BC090C;
  height: 46px;
  line-height: 46px;
  display: flex;
}

.news-header-item {
  width: 25%;
  text-align: center;
  color: #fff;
}

.current {
  color: #000000;
  background: #dee3e0;
}

.news-item {
  display: flex;
  margin: 80px 0;
}

.news-item-inside {
  margin: 5px 20px;
}

.footer {
  height: 334px;
  background: #00202E;
  width: 100%;
  margin-top: 100px;
  color: #fff;
  position: relative;
}

.footer > .block-1 {
  display: flex;
  justify-content: space-between;
  height: 280px;
  padding-top: 50px;
}

.footer-block > a {
  color: #fff;
  display: block;
  font-size: 25px;
  padding: 1px;
  font-weight: normal;
}

.footer-2 {
  text-align: center;
  border-top: 1px solid #fff;
  height: 60px;
  line-height: 60px;
  position: absolute;
  bottom: 0;
  width: 100%;
  font-size: 20px;
}

.slider .first {
  position: absolute;
  width: 100%;
  height: 500px;
}

.slider {
  position: relative;
  height: 500px;
  background-color: rgba(0, 0, 0, .5);
}

.slider p {
  position: absolute;
  top: 30%;
  left: 10%;
  color: #fff;
  font-size: 36px;
  font-weight: bold;
}

.slider button {
  position: absolute;
  top: 65%;
  width: 200px;
  height: 40px;
  left: 10%;
  font-size: 15px;
  background: #0077C8;
  color: #fff;
  font-weight: bold;
  border: 0;
  cursor: pointer;
}

.item button {
  width: 100px;
  height: 20px;
  left: 10%;
  font-size: 10px;
  background: #0077C8;
  color: #fff;
  font-weight: bold;
  border: 0;
  cursor: pointer;
  margin-left: 20px;
}

.news-item-inside span {
  color: gray;
  margin-right: 20px;
}

.header-2 button {
  width: 200px;
  height: 40px;
  left: 10%;
  font-size: 15px;
  background: #BC090C;
  color: #fff;
  font-weight: bold;
  border: 0;
  cursor: pointer;

}

.header-2 button:last-child {
  width: 150px;
  height: 40px;
  left: 10%;
  font-size: 15px;
  background: #0077C8;
  color: #fff;
  font-weight: bold;
  border: 0;
  cursor: pointer;

}
</style>
