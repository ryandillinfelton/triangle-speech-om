<template>
  <Layout>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image alt="Example image" src="~/favicon.png" width="135" />

    <h1>Triangle Speech OM</h1>

    <p>
      Let's test some content
    </p>

    <div class="services-area">
        <ServiceCard v-for="edge in $page.service.edges" :key="edge.node.name" :service="edge.node" />
    </div>

  </Layout>
</template>

<page-query>
query Services{
  service: allService{
    edges {
      node {
        name
        content
      }
    }
  }
}
</page-query>

<script>
import ServiceCard from '~/components/ServiceCard.vue'
export default {
  components: {
    ServiceCard
  },
  metaInfo: {
    title: 'Home'
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
.services-area {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    max-width: 1200px;
    margin-block: 2rem;
    gap: 2rem;
}
</style>
