<template>
    <div>
        <h2>Progress</h2>
        <div class="progress">
            <div class="progress-bar"
                 role="progressbar"
                 :style="{width: (quoteCount / maxQuotes) * 100 + '%'}"
                 aria-valuenow="0"
                 aria-valuemin="0"
                 aria-valuemax="100">{{ quoteCount }} / {{ maxQuotes }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: [
            'quoteCount',
            'maxQuotes'
        ]
    }
</script>

<style scoped>

</style>