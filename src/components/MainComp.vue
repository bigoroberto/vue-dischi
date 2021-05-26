
<template>
  <main>
    <div class="row">
      <Search 
          @selectGener ="searchGener"
          />
    </div>
    <section class="box-dischi col-10 offset-1">
      <!-- una volta che abbiamo preparato il main ad accogliere con il props quello che ci passa il padre, facciamo un v-for per ciclare tutto l'array e prenderci quello che ci interessa sapere aggiungendo anche la posizione -->
      <div 
           v-for="(disco, index) in dischi" 
           :key="index"
           class="box-disco col-md-6 col-lg-2 p-3 m-0 p-lg-0 m-lg-3 text-center"
           >
        <div class="box-background p-3">
          <!-- impostiamo l'immagine img-fluid in modo da renderla responsive e bindiamo il src e l'alt e ci aggiungiamo disco.poster e disco.title per sapere in modo dinamico il loro valore -->
          <img class="img-fluid" :src="disco.poster" :alt="disco.title">

          <!-- sempre in modo dinamico ci andiamo a prendere il titolo, autore ed anno -->
          <h3>{{disco.title}}</h3>
          <h4>{{disco.author}}</h4>
          <h4>{{disco.year}}</h4>
        </div>

      </div>
    </section>

  </main>
</template>


<script>

import Search from './Search.vue'

export default {
  name: 'MainComp',

  components:{
    Search,
  },

  data(){
    return{
      textToSearchGener : ''
    }
  },
  methods:{
    searchGener(text){
      this.textToSearchGener = text;
      console.log('arriva anche qui', this.textToSearchGener)
    }
  },
  /* con il props dico al main che il padre (APP.VUE ) 
  gli sta passando qualcosa e lo specifico dandogli il nome DISCHI e la PAROLA CHIAVE ovvero ARRAY */
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
        background-color:#2e3a46 ;
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