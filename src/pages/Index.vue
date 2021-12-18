<template>
  <Layout>
    <h1>Triangle Speech OM</h1>

    <h1>
      Services
    </h1>

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
        title
        content
        image
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
h1 {
    text-align: center;
}
</style>
