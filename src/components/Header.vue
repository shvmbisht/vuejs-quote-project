<template>
    <div class="row">
        <div class="col-sm-12">
          <h3>Quotes Added</h3>
            <div class="progress">
            <div class="progress">
            <div class="progress-bar" role="progressbar" aria-valuenow="70"
            aria-valuemin="0" aria-valuemax="100" :style="{width: (quoteCount / maxQuotes) * 100 + '%'}">
                {{ quoteCount}} / {{maxQuotes}}
            </div>
            </div>
    </div>
        </div>
        
    </div>
   
</template>
<script>
export default {
    props: ['quoteCount', 'maxQuotes']
}
</script>

<style>
h3{
    color: #2F9599;
     font-family:monospace;
}
.progress-bar{
    background-color: #2F9599;
}
</style>



