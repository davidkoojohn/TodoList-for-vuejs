<template>
  <div class="home-view">
    <div>
      <h1 class="center">{{ title }}</h1>
    </div>
    <div>
      <h2 class="center">{{ reversedMessage }}</h2>
    </div>
    <todo/>
    <p>{{ now }}</p>
    <p>Name: {{ fullName }}</p>
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
        title: 'home-view',
        firstName: 'John',
        lastName: 'Kuo'
      }
    },
    // 计算属性
    computed: {
      // 计算属性的 getter
      reversedMessage: function () {
        return this.title.split('').reverse().join('')
      },
      now: () => {
        // 计算属性缓存 vs 方法
        return Date.now()
      },
      fullName() {
        return `${this.firstName} - ${this.lastName}`
      }
    },
    // 计算属性 vs 侦听属性
    watch: {},
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
