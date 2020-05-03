<template>
    <div class="news">
        <h1>今日新闻</h1>
        <div class="single-news" v-for="singleNews in allNews" :key="singleNews">
            <h2>{{singleNews.title}}</h2>
            <article>{{singleNews.description}}</article>
        </div>
    </div>
</template>

<script>
export default {
  name: 'News',
  data () {
    return {
      allNews: []
    }
  },
  created () {
    this.$http.get('https://api.ithome.com/json/newslist/news?r=0')
      .then(function (data) {
        console.log(data)
        this.allNews = data
      })
  }
}

</script>

<style scoped>

</style>
