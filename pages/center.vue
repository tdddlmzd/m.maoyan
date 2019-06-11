<template>
    <div>
        center
        <ul>
            <li v-for="item in datalist" :key="item.id">
                <h2>{{item.nm}}</h2>
                {{item}}
            </li>
        </ul>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    data() {
        return {
            // datalist:["111","222","333","444"]
        }
    },
      asyncData() {
      return axios.get(process.server?"http://m.maoyan.com/ajax/movieOnInfoList?token=":"/ajax/movieOnInfoList?token=").then(res=>{
        console.log(res.data.movieList)
        return {
          datalist:res.data.movieList
        }
      })
  },


}
</script>
<style lang="scss" scoped>

</style>
