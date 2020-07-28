<template>
  <div class="home">
    <div class="container">
      <div class="row mt-5">
        <div class="col-md-5">
          test
        </div>
        <div class="col-md-7">
          test
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import axios from 'axios'

export default {
  name: 'Home',
  data() {
    return {
      news: []
    }
  },
  components: {
    HelloWorld
  },
  created() {
    axios.get('http://newsapi.org/v2/everything?q=bitcoin&from=2020-07-28&sortBy=popularity&apiKey=422ecef7ebfe4adeacd5e38b6222a0fb')
    .then(res => this.news = res.data)
    .catch(err => console.log(err));

    // console.log(this.news);
  }
}
</script>
