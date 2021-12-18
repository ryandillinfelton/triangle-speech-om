<template>
    <div class="rounded drop-shadow section-card">
        <h1> {{ section }} </h1>
    </div>
</template>

<script>
export default {
    props: ['section'],
}
</script>

<style lang="scss">
.section-card {
    color: var(--color-salmon) !important;
    background-color: #D16E6B;
    border-color: #D16E6B;
    padding-top: 0em;
    padding-bottom: 0em;
    h1 {
        padding: 0em;
        text-transform: uppercase;
    }
}
</style>