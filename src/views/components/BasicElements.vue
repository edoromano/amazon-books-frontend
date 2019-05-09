<template>
    <section class="section section-components pb-0" id="section-components">
        <div class="container">
            <div class="row justify-content-center">
                <div class="col-lg-12">
                    <div class="mb-1">
                        <medium class="text-uppercase font-weight-bold">Genres</medium>
                    </div>
                    <a href="#" v-bind:class="'btn btn-link text-' + randomType()" v-for="genre in genres" v-bind:key="genre.id">
                        {{genre.name}}
                    </a>
                </div>
            </div>
        </div>
    </section>

</template>
<script>
import axios from 'axios'

export default {
  name: 'Genres',
  data () {
    return {
      genres: [],
      response: ''
    }
  },
  mounted () {
    axios({ method: 'GET', 'url': 'http://localhost:3000/genres.json' }).then(result => {
      console.log(result)
      this.genres = result['data']
    }, error => {
      console.error(error)
    })
  },
  methods : {
    randomType : function(){
      var types = ['primary', 'info', 'success', 'warning', 'danger']
      var random = Math.floor(Math.random() * 5) + 1;
      return types[random];
    }
  }
}
</script>
<style>
</style>
