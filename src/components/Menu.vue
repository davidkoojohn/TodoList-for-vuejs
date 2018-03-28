<template>

  <div class="menu">
    <a href="#" v-for="(item, index) in items">
      <span v-if="item.locked"></span>
      <span v-if="item.count">{{item.count}}</span>
      {{item.title}}
    </a>
  </div>

</template>

<script>
  export default {
    name: "menus",
    data() {
      return {
        items: [
          {
            title: '星期一',
            count: 1,
            locked: true
          },
          {
            title: '星期三',
            count: 2,
            locked: false
          },
          {
            title: '星期三',
            count: 3,
            locked: true
          }
        ]
      }
    }
  }
</script>

<style scoped lang="scss">

  .menu {
    a {
      font-size: 1.4em;
    }
  }

</style>
