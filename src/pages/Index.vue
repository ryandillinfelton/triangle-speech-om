<template>
  <Layout>
    <InformationCard :information="$page.welcomeInformationCard"/>

    <SectionHeaderCard section="Services" />

    <div class="services-area">
        <ServiceCard v-for="edge in $page.services.edges" :key="edge.node.position" :service="edge.node" />
    </div>

    <SectionHeaderCard section="About" />
    <InformationCard :information="$page.aboutInformationCard"/>

    <SectionHeaderCard section="Contact" />

  </Layout>
</template>

<page-query>
query Services {
  services: allService(sortBy: "position", order: ASC) {
    edges {
      node {
        title
        image
        content
      }
    }
  },
  welcomeInformationCard: informationCard(id:1) {
    header
    image
    content
  },
  aboutInformationCard: informationCard(id:2) {
    header
    image
    content
  }
}
</page-query>

<script>
import InformationCard from '~/components/InformationCard.vue';
import ServiceCard from '~/components/ServiceCard.vue';
import SectionHeaderCard from '~/components/SectionHeaderCard.vue';

export default {
  components: {
    ServiceCard,
    SectionHeaderCard,
    InformationCard
  },
  metaInfo: {
    title: 'Home'
  }
}
</script>

<style lang="scss">
.home-links a {
  margin-right: 1rem;
}
.services-area {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    max-width: 80vw;
    gap: 2rem;
}
.img-card {
    flex: 1 1 auto;
    overflow: hidden;
}
.content-area {
    flex: 2 2 70%;
    padding: 2rem;
    h1 {
        text-align: left;
        font-size: 2rem;
        text-transform: uppercase;
    }
    p {
        font-size: 1.2rem;
    }
}

h1 {
    text-align: center;
}
</style>
