<template>
    <div class="information-card">
        <div class="img-card card">
            <img :src="information.image"/>
        </div> 
        <div class="content-area card">
            <h1>{{ information.header }}</h1>
            <div class="markdown-body mb-8" v-html="information.content" />
        </div>
    </div>
</template>

<script>
export default {
    props: ['information']
}
</script>

<style lang="scss">
.content-area {
    flex: 2 2 70%;
    padding: 2rem;
    background-color: white;
    h1 {
        text-align: left;
        font-size: 2rem;
        text-transform: uppercase;
    }
    p {
        font-size: 1.2rem;
    }
}
.information-card {
    display: flex;
    max-width: 80vw;
    justify-content: center;
    gap: 2rem;
    width: fit-content;
}
.img-card {
    flex: 1 1 auto;
    overflow: hidden;
    max-height: 32rem;
    img{
        margin: -1rem;
    }
}
</style>
