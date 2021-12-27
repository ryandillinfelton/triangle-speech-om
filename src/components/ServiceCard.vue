<template>
    <div class="service-card card">
        <div class="img-container">
            <img v-bind:src="service.image"/>
        </div>
        <div class="title-area">
            <h2>{{ service.title }}</h2>
        </div>
        <div class="content">
            <div class="markdown-body mb-8" v-html="service.content" />
        </div>
    </div>
</template>

<script>
export default {
    props: ['service'],
}
</script>

<style lang="scss">
.service-card {
    margin-bottom: 1em;
    display: flex;
    flex-direction: column;
    flex: 1 1 30%;
    @media (max-width: 600px) {
        min-width: 100%;
    }
    overflow: hidden;
    box-shadow: 0 .1rem 1rem rgba(0, 0, 0, 0.1);
    border-radius: 1em;
    background: var(--card-bg-color);
    #background: linear-gradient(to right, #FFFFFF, #ECE9E6);
    .title-area {
        text-align: center;
        padding: 0rem 0.2rem 0rem 0.2rem;
        margin: 0rem;
        background-color: var(--color-blue);
        color: white;
        h2 {
            margin: 0;
            font-size: 2rem;
            text-transform: capitalize;
            padding: 0.5rem 0em;
        }
    }
    .content {
        padding: 1rem;
        display: flex;
        flex-direction: column;
        gap: .5rem;
    }
    .img-container {
        overflow: hidden;
        img {
            width: 100%;
            height: 100%;
        }
    }
    .service-card img{
        width: 100%;
    }
}
</style>