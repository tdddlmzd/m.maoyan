<template>
  <div>
    nowingplay
    <ul>
      <li v-for="item in datalist" :key="item.filmId" @click="handeliClick(item.filmId)">
          <h2>{{item.name}}</h2>
          <img :src="item.poster">
        </li>
    </ul>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  data() {
    return {
      // datalist: ["111111", "222222", "333333", "444444"]
    };
  },
  methods: {
      handeliClick(id){
          this.$router.push(`/detail/${id}`)
      }
  },
  asyncData() {
      return axios({
        url:"https://m.maizuo.com/gateway?cityId=110100&pageNum=1&pageSize=10&type=1&k=1037144",
        headers:{
          'X-Client-Info': '{"a":"3000","ch":"1002","v":"5.0.4","e":"15586897551507533520931"}',
          'X-Host': 'mall.film-ticket.film.list'
        }
      }).then(res=>{
        console.log(res.data)
        return {
          datalist:res.data.data.films
        }
      })
  },
};
</script>
<style lang="scss" scoped>
</style>
