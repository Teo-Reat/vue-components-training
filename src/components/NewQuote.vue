<template>
    <div class="row">
        <form class="mx-auto">
            <div class="input-group m-md-3">
                <div class="input-group-prepend">
                    <span class="input-group-text">New Quote</span>
                </div>
                <textarea class="form-control" aria-label="New Quote" v-model="quote"></textarea>
            </div>
            <div class="m-md-3">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        data: function () {
            return {
                quote: ''
            }
        },
        methods: {
            createNew() {
                if (this.quote !== '') {
                    this.$emit('quoteAdded', this.quote);
                    this.quote = '';
                } else {
                    return alert('Print some text, please.');
                }
            }
        }
    }
</script>

<style scoped>
    textarea {
        resize: none;
    }
</style>