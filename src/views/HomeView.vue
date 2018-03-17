<template>
  <div class="home-view">
    <ul>
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
