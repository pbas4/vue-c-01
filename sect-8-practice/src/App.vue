<template>
    <div class="container">
        <app-header :quoteCounter="quotes.length" :maxQuotes="10"></app-header>
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @deletedQuote="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: click on a quote to delete it</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue'
    import NewQuote from './components/NewQuote.vue'
    import Header from './components/Header.vue'

    export default {
        data: function() {
            return {
                quotes: [
                    'Just a Quote to ser something'
                ],
                maxQuotes: 10
            }
        },
        methods: {
            newQuote(quote) {
                if (this.quotes.length === 10)
                    alert('Hey man the maximum is 10')
                else
                    this.quotes.push(quote);
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1)
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        }
    }
</script>

<style>
</style>
