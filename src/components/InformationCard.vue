<template>
    <div class="information-card">
        <div class="img-card card">
            <img :src="$static.informationCard.image"/>
        </div> 
        <div class="content-area card">
            <h1>{{ $static.informationCard.header }}</h1>
            <div class="markdown-body mb-8" v-html="$static.informationCard.content" />
        </div>
    </div>
</template>

<static-query>
query {
  informationCard(id:1) {
    header
    image
    content
  }
}
</static-query>

<script>
export default {
    props: [
        'image',
        'header',
        'body'
    ]
}
</script>

<style lang="scss">
    .content-area {
        background-color: white;
    }
</style>
