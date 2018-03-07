<template>
    <li
        class="list-group-item"
        style="cursor: pointer"
        @click="selectServer">
        {{ server.name }} #{{ server.id }} => Status: {{ server.status }}
    </li>
</template>

<script>
    import { serverBus } from '../../main'

    export default {
        props: ['server'],
        methods: {
            selectServer() {
                serverBus.$emit('selectedServer', this.server);
            }
        }
    }
</script>

<style>

</style>
