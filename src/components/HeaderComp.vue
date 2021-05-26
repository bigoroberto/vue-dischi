
<template>
  <header>
    <div class="box-logo col-1 offset-1">
        <div class="logo">Spotify</div>
    </div>


  </header>
</template>

<script>

import Search from '@/components/Search.vue'

export default {
 name:'HeaderComp',

}


</script>

<style lang="scss" scoped>
header{
  height: 70px;
  background-color:#2E3A46 ;
  display: flex;
  align-items: center;
  .box-logo{
    .logo{
      height: 50px;
      line-height: 46px;
      width: 50px;
      border-radius: 50%;
      background-color: #1ED560
    }
  }
}
</style>