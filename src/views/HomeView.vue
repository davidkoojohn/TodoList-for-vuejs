<template>
  <div class="home-view">

    <div class="menu-container">
      <menus></menus>
    </div>

  </div>
</template>

<script>

  import Menus from '../components/Menu'

  export default {
    name: 'home-view',
    components: {
      Menus
    },
    data() {
      return {}
    },
    watch: {},
    methods: {}
  }

</script>

<style scoped lang="scss">

  .home-view {
    .center {
      text-align: center;
    }
  }

</style>
