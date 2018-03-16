<template>
  <div class="hello center">
    <h1>{{ msg }}</h1>
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

<style scoped>

  .center {
    text-align: center;
  }

</style>
