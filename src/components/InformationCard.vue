<template>
    <div class="information-card">
        <div class="img-card card">
            <img :src="image"/>
        </div> 
        <div class="content-area card">
            <h1>{{ header }}</h1>
            <p>{{ body }}</p>
        </div>
    </div>
</template>

<page-query>

</page-query>

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
