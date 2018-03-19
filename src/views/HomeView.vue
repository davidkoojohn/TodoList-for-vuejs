<template>
  <div class="home-view">
    <ul>
      <li v-for="(item, index) in todos" :key="index">
        <input type="checkbox" :checked="item.done"/>
        <strong @click="tryDo">{{ item.title }}{{item.id}}</strong>
      </li>
    </ul>
    <div>
      <input v-model="newTodoText"
             v-on:keyup.enter="addNewTodo"
             placeholder="Add new todo"/>
    </div>
    <router-link :to="{ path: '/signin'}">Sign In</router-link>
    <demo :current="2"
          :total="40"
          :currentChange="whenChange"></demo>
  </div>
</template>

<script>

  import Todo from '../components/Todo'
  import Demo from '../components/Demo'

  export default {
    name: 'home-view',
    components: {
      Todo,
      Demo
    },
    data() {
      return {
        newTodoText: '',
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
    watch: {
      todos(val, val2) {
        console.log(val)
        console.log(val2)
      }
    },
    methods: {
      tryDo: (e) => {
        console.log(e)
      },
      addNewTodo() {
        const ID = this.todos[this.todos.length -1].id + 1
        this.todos.push({
          id: ID,
          title: this.newTodoText,
          done: false
        })
        this.newTodoText = ''
      },
      whenChange(item) {
        console.log(item)
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
