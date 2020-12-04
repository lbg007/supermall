<template>
  <div id="home" >
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper class="banner" :banners="banners"/>
    <recommend-view :recommends="recommends"/>
    <feature-view/>
    <tab-control class="tab-control" :titles="['流行', '新款', '精选']"/>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li><li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li><li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li><li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
  </div>
</template>

<script>
import HomeSwiper from './childComps/HomeSwiper'
import RecommendView from './childComps/RecommendView'
import FeatureView from './childComps/FeatureView'

import NavBar from 'components/common/navbar/NavBar'
import TabControl from 'components/content/tabControl/TabControl'

import {getHomeMultidata} from "network/home";
  export default {
    name: "Home",
    components:{
      HomeSwiper,
      RecommendView,
      FeatureView,

      NavBar,
      TabControl
    },
    data() {
      return {
        banners:[],
        recommends:[]
      }
    },
     created() {
       getHomeMultidata().then(res=>{
        //  console.log(res)
        this.banners = res.data.banner.list
        this.recommends = res.data.recommend.list
      })
     },
  }
</script>

<style scoped>
.home-nav{
  background-color:var(--color-tint);
    color: #fff;
    /**Fixed定位使元素的位置与文档流无关，因此不占据空间。 */
    position:fixed;
    top: 0px;
    right: 0px;
    left: 0px;
    z-index: 1;
    
}
#home{
  padding-top: 44px;
}
.tab-control{
  position: sticky;
  top: 44px;
}
</style>
