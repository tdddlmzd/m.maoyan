<template>
  <div>
    cinema
    <el-carousel height="150px">
      <el-carousel-item v-for="item in bannerList" :key="item.bannerId">
        <img :src="item.imgUrl">
      </el-carousel-item>
    </el-carousel>
    <el-row>
      <el-button>默认按钮</el-button>
      <el-button type="primary">主要按钮</el-button>
      <el-button type="success">成功按钮</el-button>
      <el-button type="info">信息按钮</el-button>
      <el-button type="warning">警告按钮</el-button>
      <el-button type="danger">危险按钮</el-button>
    </el-row>
  </div>
</template>
<script>
import axios from 'axios'
export default {
    asyncData() {
        return axios({
            url:"https://m.maizuo.com/gateway?type=2&cityId=110100&k=4478689",
            headers:{
                'X-Client-Info': '{"a":"3000","ch":"1002","v":"5.0.4","e":"15586897551507533520931"}',
                'X-Host': 'mall.cfg.common-banner'
            }
        }).then(res=>{
            console.log(res.data.data)
            return {
                bannerList:res.data.data
            }
        })
    },
};
</script>
<style scoped>
.el-carousel__item img {
  width:100%
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
</style>
