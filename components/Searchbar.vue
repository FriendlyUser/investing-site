<template>
  <div>
    <vs-input v-model="query" type="search" autocomplete="off">
      <template #icon>
        <i class="material-icons">search</i>
      </template>
    </vs-input>
    <div v-if="articles.length" class='sr-wrapper'>
      <ul class='sr-results'>
        <li v-for="article of articles" :key="article.slug" class="sr-item">
          <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }" class="sr-link">{{ article.title }}</NuxtLink>
        </li>
      </ul>
    </div>
  </div>
</template>
<style>
.sr-wrapper {
  position: absolute;
  padding-top: 15px;
  border-radius: 5px;
}
.sr-results {
  color: var(--vs-primary);
  background-color: #242145;
  list-style: none;
  padding: 15px;
  width: 200px;
  border-radius: 15px;
}
.sr-item {
  padding-top: 10px;
  background-color: var(--vs-success);
  color: white;
}
.sr-item:first-of-type {
  padding-top: 0px;
}
.sr-link {
  color: white;
  text-align: center;
}
</style>
<script>
export default {
  data () {
    return {
      query: '',
      articles: []
    }
  },
  watch: {
    async query (query) {
      if (!query) {
        this.articles = []
        return
      }

      this.articles = await this.$content('articles')
        .only(['title', 'slug'])
        .sortBy('createdAt', 'asc')
        .limit(12)
        .search(query)
        .fetch()
    }
  }
}
</script>