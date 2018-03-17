<template>
  <div class="container">
    <ul>
      <li>
        <input type="checkbox" checked="checked"/>
        <strong>代办事件</strong>
      </li>
      <li>
        <input type="checkbox" checked="checked"/>
        <strong>代办事件</strong>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "todo",
    data () {
      return {}
    }
  }
</script>

<style scoped lang="scss">

  .container {
    ul {
      border: 1px solid #eee;

      li {
        padding: 10px 0;
        border-bottom: 1px solid #eee;

        &:last-child {
          border: none;
        }
      }
    }
  }

</style>
