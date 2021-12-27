<template>
    <div class="contact-card card">
        <h2> {{ type }} </h2>
        <h3> {{ value }} </h3>
    </div>
</template>

<script>
export default {
    props: [
        'type',
        'value'
    ]
}
</script>

<style lang="scss">
.contact-card {
    color: white;
    text-align: center;
    background-color: var(--color-blue);
    flex: 1 1 48%;
    h2 {
        text-transform: uppercase;
    }
    h3 {
        margin-top: 0rem;
        @media (max-width: 600px) {
            font-size: 100%;
        }
    }
}
</style>
