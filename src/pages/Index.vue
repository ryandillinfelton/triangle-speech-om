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

    <div class="contact-area">
        <ContactCard type="Phone" value="(919) 972-8134" />
        <ContactCard type="Email" value="Diane@TriangleSpeechOM.com" />
    </div>
    <!--
    <div class="contact-card card">
        <h2> Email </h2>
        <a href="mailto:Diane@TriangleSpeechOM.com">Diane@TriangleSpeechOM.com</a>
    </div>
    -->

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
import ContactCard from '~/components/ContactCard.vue';

export default {
  components: {
    ServiceCard,
    SectionHeaderCard,
    InformationCard,
    ContactCard
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
    //max-width: var(--global-content-width);
    gap: 2rem;
    @media only screen and (max-width: var(--bp-smallest)) {
      flex-direction: column;
    }
    @media only screen and (min-width: var(--bp-medium)) {
      flex-direction: row;
    }
    justify-content: space-evenly;
}
.contact-area {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
    gap: 2rem;
}
h1 {
    text-align: center;
}
</style>
