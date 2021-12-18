<template>
  <Layout>
    <InformationCard  />
    
    <!--
    <div class="information-card">
        <div class="img-card card">
            <img src="/uploads/logo.png"/>
        </div> 
        <div class="content-area card">
            <h1>Triangle Speech and Orofacial Myology</h1>
            <p>Welcome to Triangle Speech & Orofacial Myology. We are glad you are exploring our site and hope you find all the information you need to determine if this is the right practice to meet your needs or those of your child. Our goal is to find the best treatment approach to meet the concerns of each individual. At Triangle Speech & Orofacial Myology, we will complete a thorough evaluation and set up a treatment plan for therapy sessions as well as a home plan to ensure the quickest progress possible. </p>
        </div>
    </div>
    -->

    <SectionHeaderCard section="Services" />

    <div class="services-area">
        <ServiceCard v-for="edge in $page.service.edges" :key="edge.node.position" :service="edge.node" />
    </div>

    <SectionHeaderCard section="About" />

    <SectionHeaderCard section="Contact" />

  </Layout>
</template>

<page-query>
query Services {
  service: allService(sortBy: "position", order: ASC) {
    edges {
      node {
        title
        image
        content
      }
    }
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
.information-card {
    display: flex;
    max-width: 80vw;
    justify-content: center;
    gap: 2rem;
    height: 24rem;
    width: fit-content;
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
