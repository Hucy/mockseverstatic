<template>
    <div class="edit-comb">
        <TypeSync v-if='editType=="sync"' @sync='syncHandle'></TypeSync>
    </div>        
</template>

<script>
    import TypeSync from './sub-edit/type-sync'
    export default {
        props: ['editType'],
        components: {
            TypeSync
        },
        methods: {
            syncHandle(value) {
                console.log(value)
            }
        }
    }
</script>
<style scoped>
    .edit-comb {
        margin-top: .5em;
        padding: .5em;
        background: #EFF2F7;
        border-radius: 3px;
        height: 93%;
    }
</style>