<template>
  <div class="home-view">
    <div>
      <h1 class="center">{{ title }}</h1>
    </div>
    <div>
      <h2 class="center">{{ reversedMessage }}</h2>
    </div>
    <todo/>
  </div>
</template>

<script>

  import Todo from '../components/Todo'

  export default {
    name: 'home-view',
    components: {
      Todo
    },
    data() {
      return {
        title: 'home-view'
      }
    },
    computed: {
      // 计算属性的 getter
      reversedMessage: function () {
        return this.title.split('').reverse().join('')
      }
    },
    methods: {

    }
  }

</script>

<style scoped lang="scss">

  .home-view {
    .center {
      text-align: center;
    }
  }

</style>
