<template>
  <div class="signin-view">
    <h1 class="center">{{ title }}</h1>
  </div>
</template>

<script>

  export default {
    name: 'signin-view',
    components: {},
    data() {
      return {
        title: 'signin-view'
      }
    }
  }

</script>

<style scoped lang="scss">

  .signin-view {
    color: brown;

    .center {
      text-align: center;
    }
  }

</style>
