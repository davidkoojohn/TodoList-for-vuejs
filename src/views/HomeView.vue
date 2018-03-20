<template>
  <div class="home-view">

    <div class="menu-container">
      <menus></menus>
    </div>

    <div>
      <router-link to="/signin" target="_blank">Sign In</router-link>
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
    mounted() {
      console.log(this.$route.path)
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
