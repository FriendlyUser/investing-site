<template>
  <vs-navbar fixed center-collapsed v-model="active">
    <template #left>
      <nuxt-link to="/" >
        <img src="https://s.gravatar.com/avatar/d5a6e001f027e8cf3dbf048a926baa77?s=20%27)" alt="title">
      </nuxt-link>
    </template>
    <vs-navbar-item :active="active == 'blog'" id="blog">
      <nuxt-link to="/blog" class='dli-link'>
        Blog
      </nuxt-link>
    </vs-navbar-item>
    <vs-navbar-item :active="active == 'docs'" id="docs">
      Documents
    </vs-navbar-item>
    <vs-navbar-item :active="active == 'components'" id="components">
      Components
    </vs-navbar-item>
    <vs-navbar-item :active="active == 'license'" id="license">
      license
    </vs-navbar-item>
    <template #right>
      <Searchbar />
    </template>
  </vs-navbar>
</template>
<style scoped>
.dli-link {
  text-decoration: none;
  color: var(--vs-background);
}
</style>
<script>
  export default {
    data:() => ({
      active: 'blog'
    })
  }
</script>