<template>
  <div class="home-view">
    <ul>
      <!--
      v-bind:checked="" === :checked=""
      v-on:click="" === @click=""
      -->
      <li v-for="(item, index) in todos" :key="item.id">
        <input type="checkbox" :checked="item.done"/>
        <strong @click="tryDo">{{ item.title }}</strong>
      </li>
    </ul>
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
        todos: [
          {
            id: 1,
            title: 'will do 1',
            done: false
          },
          {
            id: 2,
            title: 'will do 2',
            done: true
          },
          {
            id: 3,
            title: 'will do 3',
            done: false
          },
          {
            id: 4,
            title: 'will do 4',
            done: true
          }
        ]
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
      tryDo: (e) => {
        console.log(e)
      }
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
