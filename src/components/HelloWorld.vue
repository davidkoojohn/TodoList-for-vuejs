<template>
  <div class="hello">
    <h1 class="center">{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome TodoList'
    }
  }
}
</script>

<style scoped="sass" lang="scss">

  .hello {
    .center {
      text-align: center;
    }
  }

</style>
