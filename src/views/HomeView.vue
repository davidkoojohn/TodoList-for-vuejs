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

  </div>
</template>

<script>

  export default {
    name: 'home-view',
    components: {},
    data() {
      return {
        newTodoText: '',
        todos: [
          {
            id: 1,
            title: 'will do 1',
            done: false
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
