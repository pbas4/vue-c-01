<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">Please Select Server</p>
        <p v-else>{{ server.name }} #{{ server.id }} => Status: {{ server.status }}</p>
        <button :disabled="!server" @click="changeStatus">Change status</button>
        <button :disabled="!server" @click="unselectServer">Unselect server</button>
    </div>

</template>

<script>
    import { serverBus } from '../../main'

    export default {
        data: function() {
            return {
                server: null
            }
        },
        methods: {
            changeStatus() {
                this.server.status = 'Normal Changed'
            },
            unselectServer() {
                this.server = null
            }
        },
        created() {
            serverBus.$on('selectedServer', (server) => {
                this.server = server
            });
        }
    }
</script>

<style>

</style>
