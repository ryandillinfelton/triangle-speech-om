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
.information-card {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2rem;
}
.content-area {
    flex: 1 1 40%;
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
.img-card {
    background-color: var(--color-blue);
    flex: 0 1 800px;
    overflow: hidden;
    img{
        min-height: 100%;
        min-width: 100%;
        max-width: 100%;
    }
}
</style>
