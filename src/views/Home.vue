<template>
  <div class="home">
    <div class="container">
      <div class="row mt-5">
        <div class="col-md-5">
          <div v-bind:key="noticias.id" v-for="noticias in news.articles">
            <h3>{{noticias.author}}</h3>
            <h5>{{noticias.title}}</h5>

            <button class="btn-sm btn-primary mb-3" v-on:click="newsDetail(noticias)">Details</button>
          </div>
        </div>
        <div class="col-md-7">
          <NewsDetails v-bind:newsdetail="newsdetail"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import NewsDetails from '@/components/NewsDetails.vue'
import axios from 'axios'

export default {
  name: 'Home',
  data() {
    return {
      news: [],
      newsdetail: Object
    }
  },
  components: {
    NewsDetails
  },
  methods: {
    newsDetail(id) {
      this.newsdetail = id;
      console.log(this.newsdetail);
    }
  },
  created() {
    axios.get('http://newsapi.org/v2/everything?q=bitcoin&from=2020-07-28&sortBy=popularity&apiKey=422ecef7ebfe4adeacd5e38b6222a0fb')
    .then(res => this.news = res.data)
    .catch(err => console.log(err));

    // console.log(this.news);
  }
}
</script>
