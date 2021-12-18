<template>
  <Layout>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image alt="Example image" src="~/favicon.png" width="135" />

    <h1>Triangle Speech OM</h1>

    <p>
      Let's test some content
    </p>

    <!--
    <div v-for="edge in $page.services.edges" :key="edge.node.name">
      <h2>{{ edge.node.name }}</h2>
      <p>{{ edge.node.content }}</p>
    </div>
    -->

  </Layout>
</template>

// <page-query>
// query Services{
//   service: allService{
//     edges {
//       node {
//         name
//         content
//       }
//     }
//   }
// }
// </page-query>

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
