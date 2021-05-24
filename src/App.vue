<template>
  <div id="app">
    <HeaderComp />
    
    <MainComp :dischi="albums"/>
  </div>
</template>

<script>
import axios from 'axios';
import HeaderComp from '@/components/HeaderComp.vue';
import MainComp from '@/components/MainComp.vue';

export default {
  name: 'App',
  
  components: {
    HeaderComp,
    MainComp,
  },

  data(){
    return{
      axios,
      albums:[],
    }
  },

  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(res => {
      console.log(res.data)
      this.albums = res.data.response
    }).catch(err => {
      console.log(err)
    })
  }
}
</script>


<style lang="scss">

@import '@/assets/style/general';

</style>