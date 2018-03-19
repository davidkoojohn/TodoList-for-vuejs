
<!-- html标签 -->
<template>
  <div class="demo">
    <ul>
      <li @click="pre"> < </li>
      <li v-for="item in show_page_number"
          :class="{active: item == current_index}"
          @click="setIndex(item)"
      >
        {{item}}
      </li>
      <li @click="next"> > </li>
    </ul>
  </div>
</template>


<!-- js脚本，定义组件，实现逻辑 -->
<script>
  export default {
    // name: 组件名称，使用时将把 name 做为标签名 <name></name>
    name: "demo",

    // props: 组件的属性，用于接收传入参数，在组件中可以使用 this.prop_name 引用
    props: {
      current: {
        type: Number,
        default: 1
      },
      total: {
        type: Number
      },
      currentChange: {
        type: Function
      }
    },
    // data: 组件初始化数据，定义一个返回对象函数
    data() {
      return {
        show_page_number: [],
        display_limit: 8,
        current_index: this.current
      }
    },
    // beforeCreate, created, beforeMount, mounted, beforeDestroy, destroy: 生命周期函数
    // beforeUpdate, updated
    mounted() {
      // console.log(this.current)
      // console.log(this.total)
      // console.log(this.currentChange)
      this.refreshPage()
    },
    // methods: 方法
    methods: {
      refreshPage(e) {
        this.show_page_number = []
        for (let i = 1; i <= this.display_limit; i++) {
          this.show_page_number.push(i)
        }

        if (this.total <= this.display_limit) { return }
        let begin = this.current_index - 3
        let end = this.current_index + 3
        begin = begin <= 1 ? 1 : begin
        end = end <= this.display_limit ? this.display_limit : end
        begin = begin >= this.total - this.display_limit ? this.total - this.display_limit : begin
        end = end >= this.total ? this.total : end

        let arr = this.show_page_number.slice(begin - 1, end)
        this.show_page_number = arr
      },
      pre() {
        let current = this.current_index
        if (current <= 1) {
          return
        }
        this.setIndex(current - 1)
      },
      next() {
        let current = this.current_index
        if (current >= this.total) {
          return
        }
        this.setIndex(current + 1)
      },
      setIndex(index) {
        this.current_index = index
        this.refreshPage()
      }
    }

    // Vue.use(component) install 方法

  };
</script>

<!-- 样式 -->
<style scoped lang="scss">
  /* scoped 防止样式污染全局 */
  li{
    list-style: none;
    display: inline-block;
    margin: 5px -0.5px;
    border: 1px solid #2c3e50;
    padding: 5px;
    min-width: 30px;
    min-height: 30px;
    line-height: 200%;
    cursor: pointer;
    transition: all 0.3s;
    user-select: none;
  }
  .active, li:hover{
    background-color: rgba(65, 182, 131, .5);
    color: #ffffff;
    border-color: rgba(65, 182, 131, .5);
  }
  a{
    display: inline-block;
    color: inherit;
  }
  .clearfix{
    clear: both;
  }

</style>
