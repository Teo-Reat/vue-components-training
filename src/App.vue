<template>
    <div id="app" class="container">
        <app-header :maxQuotes="maxQuotes" :quoteCount="quotes.length"></app-header>
        <app-new-quote @quoteAdded="addNewQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @startDeleteQuote="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a quote to delete it.</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from "./components/QuoteGrid";
    import NewQuote from "./components/NewQuote";
    import Header from "./components/Header";

    export default {
        data: function () {
            return {
                quotes: ['Just a quote to see something.'],
                maxQuotes: 10,
            }
        },
        components: {
            'appQuoteGrid': QuoteGrid,
            'appNewQuote': NewQuote,
            'appHeader': Header,
        },
        methods: {
            addNewQuote(quote) {
                if (this.quotes.length >= this.maxQuotes) {
                    return alert('Please, delete quote first!')
                } else {
                    this.quotes.push(quote);
                }
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        }
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
