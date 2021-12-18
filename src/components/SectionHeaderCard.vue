<template>
    <div class="card section-card">
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
    color: white;
    background-color: var(--color-salmon);
    border-color: var(--color-salmon) !important;
    margin: 2rem 0rem;
    h1 {
        padding: 0em;
        text-transform: uppercase;
    }
}
</style>