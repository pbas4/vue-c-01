<template>
  <div class="col-xs-12 col-sm-6">
    <ul class="list-group">
      <app-server
        :key="server.id"
        v-for="server in servers"
        :server="server">
      </app-server>
    </ul>
  </div>
  
</template>

<script>
  import Server from './Server.vue'
  
  export default {
    data: function() {
      return {
        servers: [
          { id: 1, status: 'Normal', name: 'Server' },
          { id: 2, status: 'Critical', name: 'Server' },
          { id: 3, status: 'Unknown', name: 'Server' },
          { id: 4, status: 'Normal', name: 'Server' }
        ]
      }
    },
    components: {
      appServer: Server
    }
  }
</script>

<style scoped>

</style>
