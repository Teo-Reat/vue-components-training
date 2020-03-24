<template>
    <div class="row m-md-3">
        <app-quote v-for="(quote, key) in quotes" :key="key" @click.native="deleteQuote(key)">{{ quote }}</app-quote>
    </div>
</template>

<script>
    import Quote from './Quote';

    export default {
        props: ['quotes'],
        components: {
            'appQuote': Quote
        },
        methods: {
            deleteQuote(key) {
                this.$emit('startDeleteQuote', key);
            }
        }
    }
</script>

<style>

</style>