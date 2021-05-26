<template>
  <div>
    <form class="d-flex mb-5 mt-5">
      <div class="flex-grow-1 d-flex justify-content-center alings-item-center">
        <h1>Scegli il genere che preferisci ascoltare</h1>
        <select class="ms-5" name="Scelta Genere" id="SceltaGenere" 
        @click.prevent="startGener"
        v-model="stringGener"
        >
          <option value="rock">{{stringGener.}}</option>
          <option value="pop">POP</option>
          <option value="3">JAZZ</option>
          <option value="4">METAL</option>
        </select>
      </div>
    </form>
  </div>
  
</template>

<script>
export default {
  name: 'Search.vue',

  data(){
    return{
      stringGener : ''

    }
  },
  methods:{
    startGener(){
      this.$emit("selectGener" , this.stringGener )
      console.log(this.stringGener)
    }
  },
  computed:{

  }
}
</script>

<style lang="scss" scoped>
h1{
  font-size: 40px;
  color: gray;
  background-color: #2e3a46;
  padding: 10px;
}

</style>