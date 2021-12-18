<template>
    <div class="rounded drop-shadow service-card">
        <div class="img-container">
            <img v-bind:src="service.image"/>
        </div>
        <div class="content">
            <h2>{{ service.title }}</h2>
            <div class="markdown-body mb-8" id="article-area" v-html="service.content" />
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
    width: clamp(20rem, calc(20rem + 2vw), 22rem);
    overflow: hidden;
    box-shadow: 0 .1rem 1rem rgba(0, 0, 0, 0.1);
    border-radius: 1em;
    background: var(--card-bg-color);
    #background: linear-gradient(to right, #FFFFFF, #ECE9E6);
}

.service-card .content {
    padding: 1rem;
    display: flex;
    flex-direction: column;
    gap: .5rem;
}

.service-card .content h2 {
    text-align: center;
    font-size: 1.5rem;
    text-transform: capitalize;
    padding: 0.2rem;
    margin: 0rem;
}

.service-card .img-container {
    height: 15em;
    overflow: hidden;
}
.service-card img{
    width: 100%;
}
</style>