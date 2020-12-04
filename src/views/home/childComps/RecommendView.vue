<template>
  <div class="recommend">
    <div v-for="(item,index) in recommends" :key="index" class="recommend-item">
      <a :href="item.link">
        <img :src="item.image" alt="">
        <div>{{item.title}}</div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
    name:'RecommendView',
    components:{

    },
     props: {
      recommends: {
        type: Array,
        default() {
          return []
        }
      }
    },
}
</script>

<style>
.recommend {
    display: flex;
   
    text-align: center;
    font-size: 12px;

    padding: 10px 0 20px;
    border-bottom: 10px solid #eee;
}
.recommend-item img{
    width: 80%;
    
    
}

</style>