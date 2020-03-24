<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel-body quote rounded-lg border">
            <slot></slot>
        </div>
    </div>
</template>

<script>

</script>

<style>
    .panel-body {
        font-size: 24px;
        color: #6e6e6e
    }

    .quote {
        cursor: pointer;
    }

    .quote:hover {
        background: #ffe2e2;
    }
</style>