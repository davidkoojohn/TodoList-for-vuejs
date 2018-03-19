<template>
  <div class="signin-view">
    <h1 class="center">{{ title }}</h1>
  </div>
</template>

<script>

  import Todo from '../components/Todo'

  export default {
    name: 'signin-view',
    components: {
      Todo
    },
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
