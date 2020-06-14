<template>
  <div class="home">
    <h1>This is an 2-2 page</h1>
    <h1>This is {{res}}</h1>
    <h1>This is {{res.data.tittle}}</h1>

  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'axios2-2', 
  components: {
  },
  created(){
    axios.get('/data.json',{
      params:{
        id:12
      }
    }).then((res)=>{
      console.log(res)
    })
    //get请求写法1

    axios({
        method:'get',
        url:'/data.json',params:{
          id:12
        }
    }).then(res=>{
        console.log(res)
        console.log('zheshi')
        console.log(res.data)
        console.log('tittle')
        console.log(res.data.tittle)
    })
    //get请求写法2
  }
}
</script>
