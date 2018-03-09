<template>
  <div>
    <div class="title">
      <slot name="title">Not shown if slot has content, this is default content</slot>
      <span style="color: #ccc"><slot name="subtitle">The subtitle</slot></span>
    </div>
    <hr>
    <div>
      <slot></slot>
    </div>
  </div>
</template>

<script>
  export default {
    
  }
</script>

<style scoped>
  div {
    border: 1px solid red;
    box-shadow: 1px 1px 2px tomato;
    padding: 30px;
    margin: 30px auto;
    text-align: center;
  }

  h2 {
    color: tomato;
  }

  .title {
    font-style: italic;
  }
</style>
