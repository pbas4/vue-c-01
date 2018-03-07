<template>
  <div class="container">
    <app-header></app-header>
    <hr>
    <div class="row">
      <server-list></server-list>
      <app-server-details></app-server-details>
    </div>
    <hr>
    <div class="row">
      <app-footer></app-footer>
    </div>
  </div>
</template>

<script>
  import Footer from './components/shared/Footer.vue'
  import Header from './components/Shared/Header.vue'
  import ServerList from './components/Server/ServerList.vue'
  import ServerDetails from './components/Server/ServerDetails.vue'

  export default {
    components: {
      appHeader: Header, // Vue converts it to dashed
      ServerList, // ES6 converts it to ServerList: ServerList
      'app-server-details': ServerDetails,
      'app-footer': Footer
    }
  }
</script>

<style>

</style>
