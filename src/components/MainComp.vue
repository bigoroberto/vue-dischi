
<template>
  <main class="d-flex">
    <section class="box-dischi col-10 offset-1">
      <div 
      v-for="(disco, index) in dischi" :key="index"
      class="box-disco col-12 col-md-6 col-lg-2 p-3 m-0 p-lg-0 m-lg-3 text-center">
        <div class="box-background p-3">
          <img class="img-fluid" :src="disco.poster" :alt="disco.title">
          <h3>{{disco.title}}</h3>
          <h4>{{disco.author}}</h4>
          <h4>{{disco.year}}</h4>
        </div>

      </div>
    </section>

  </main>
</template>


<script>
export default {
  name: 'MainComp',
  props:{
    dischi:Array
  }
}
</script>

<style lang="scss" scoped>
main{
  background-color:#1E2D3B ;
  padding: 90px 0;
  .box-dischi{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    .box-disco{
      .box-background{
        background-color:#1e2d3b ;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        height: 100%;
        img{
          width: 100%;
        }
        h3{
          color: #fff;
          font-size: 20px;
          text-transform: uppercase;
          font-weight: bold;
          margin:20px 0;
        }
        h4{
          font-size: 15px;
          color:#655e5b;    
          font-weight: bold;
        }
      }
    }
  }
}
</style>