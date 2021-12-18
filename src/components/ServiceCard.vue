<template>
    <div class="service-card">
        <div class="content">
            <h2>{{ service.name }}</h2>
            <div class="markdown-body mb-8" id="article-area" v-html="service.content" />
        </div>
    </div>
</template>

<script>
    export default {
        props: ['service'],
    }
</script>

<style>
.service-card {
    margin-bottom: 1em;
    display: flex;
    flex-direction: column;
    width: clamp(20rem, calc(20rem + 2vw), 22rem);
    overflow: hidden;
    box-shadow: 0 .1rem 1rem rgba(0, 0, 0, 0.1);
    border-radius: 1em;
    background: #ECE9E6;
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
}
</style>