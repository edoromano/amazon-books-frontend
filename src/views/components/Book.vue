<template>
  <section class="section section-components pb-0" id="section-components">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-12">
          <div class="mb-1">
            <small class="text-uppercase font-weight-bold">Book</small>
          </div>
          <ul>
            <li >
               Title: {{book.title}}
            </li>
            <li >
              ISBN: {{book.isbn}}
            </li>
            <li >
              Author: {{book.author}}
            </li>
            <li >
              Rating: {{book.average_rating}}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>

</template>
<script>
import axios from 'axios'

export default {
  name: 'Book',
  data () {
    return {
      book: {},
      response: ''
    }
  },
  mounted () {
    var api_url = 'http://localhost:3000/books/{}.json'.replace('{}', this.$route.query.id)
    axios({ method: 'GET', 'url': api_url }).then(result => {
      this.book = result['data']
    }, error => {
      console.error(error)
    })
  }
}
</script>
<style>
</style>
