<template>
  <div class="row test">
    <div class="col-xs-12">
      <header>
        <h1>{{ title }}</h1>
      </header>
    </div>
  </div>
</template>

<script>
  export default {
    data: function() {
      return {
        title: 'Server Status'
      }
    }
  }
</script>

<style scoped>
  /* .test {
    border-bottom: 1px solid lightgray;
  } */
</style>
