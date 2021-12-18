<template>
  <Layout>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image alt="Example image" src="~/favicon.png" width="135" />

    <h1>Triangle Speech OM</h1>

    <p>
      Let's test some content
    </p>

    <div v-for="edge in $page.service.edges" :key="edge.node.name">
      <h2>{{ edge.node.name }}</h2>
      <div class="markdown-body mb-8" id="article-area" v-html="edge.node.description" />
    </div>

  </Layout>
</template>

<page-query>
query Services{
  service: allService{
    edges {
      node {
        name
        description
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
