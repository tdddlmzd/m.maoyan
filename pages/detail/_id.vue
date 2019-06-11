<template>
    <div>
        动态datail----{{this.$route.params.id}}
        {{filmfoo}}
    </div>
</template>
<script>
import axios from 'axios'
export default {
    layout: 'detailtemplate',
    asyncData({params}) {
      return axios({
        url:`https://m.maizuo.com/gateway?filmId=${params.id}&k=608638`,
        headers:{
          'X-Client-Info': '{"a":"3000","ch":"1002","v":"5.0.4","e":"15586897551507533520931"}',
          'X-Host': 'mall.film-ticket.film.info'
        }
      }).then(res=>{
        // console.log(res.data)
        return {
          filmfoo:res.data.data.film
        }
      })
  },
}
</script>
<style lang="scss" scoped>
</style>
