<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
        <app-new-Quote @quoteAdded="newQuote"></app-new-Quote>
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: Click on the Quote to delete it
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid'
     import NewQuote from './components/NewQuote'
     import Header from './components/Header'
    export default {
         data:function(){
            return {
                quotes: [
                    'This is some Quote by me',
                    'this is second number quote'
                ],
                maxQuotes: 10
                }
        },
        methods: {
            newQuote(quote){
                if(this.quotes.length >= this.maxQuotes){
                    alert("Please delete the quotes first");
                }
                if(quote.length > 0 && quote.length <21){
                    this.quotes.push(quote);
                }else{
                    alert("your quote is too long to insert ");
                }
                
                
            },
            deleteQuote(index){
                this.quotes.splice(index,1);
            }
        },
        components:{
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote ,
            appHeader: Header
        }
    }
</script>

<style>
</style>
