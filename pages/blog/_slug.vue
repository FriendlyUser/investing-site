<template>
  <div class='blog-wrapper'>
    <div class="container">
      <div class="grid">
        <vs-row>
          <vs-col xs ="12" sm="9" lg="8">
            <article>
              <nuxt-content :document="article" />
            </article>
          </vs-col>
          <vs-col xs="12" sm="3" lg="4">
            <h3 class='toc-title'>On This Page</h3>
            <ul class='toc-list'>
              <li
                v-for="link of article.toc"
                :key="link.id"
                :class="{ 'toc2': link.depth === 2, 'toc3': link.depth === 3 }"
              >
                <NuxtLink :to="`#${link.id}`" >{{ link.text }}</NuxtLink>
              </li>
            </ul>
          </vs-col>
        </vs-row>
      </div>
      <BlogLinks />
    </div>
  </div>
</template>

<style scoped>
  .blog-wrapper {
    padding-top: 150px;
  }
  .toc-title {
    color: gray;
  }
  .toc-list {
    list-style: none;
  }

  .toc2 > a, .toc3 > a {
    color: gray;
  }
</style>
<script>
  export default {
    async asyncData({ $content, params }) {
      const article = await $content('articles', params.slug).fetch()
      return { article }
    }
  }
</script>