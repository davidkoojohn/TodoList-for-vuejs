## Vuex note

1. 创建一个用来共享的存储，在这个例子中它将通过 vue/vuex 注入到组件当中。
2. 定义组件可以调用的 actions，它们仍然是集中定义的。
3. 定义实际接触存储状态的 mutations。我们这么做，actions 就可以形成不止一个 mutation，或者执行逻辑去决定调用哪一个 mutation。这意味着你再也不用担心组件当中的业务逻辑了，成功！
4. 当状态更新时，任何拥有 getter，动态属性和映射到 store 的组件都会被立即更新。

```
// main.js
import store from './vuex/store'

new Vue({ // eslint-disable-line no-new
  el: '#app',
  render: (h) => h(App),
  store: store
})

// store.js
export default new Vuex.Store({
  state: {
    messages: []
  },
  actions: {
    newMessage ({commit}, msg) {
      commit('NEW_MESSAGE', msg)
    }
  },
  mutations: {
    NEW_MESSAGE (state, msg) {
      state.messages.push(msg)
    }
  },
  strict: debug
})
// 和我们自己创建的对象非常相似，但是多了一个 mutations 对象。

// Client.vue
<div class="row">
  <div class="col">
    <client clientid="Client A"></client>
  </div>
  <div class="col">
    <client clientid="Client B"></client>
  </div>
</div>

<script>
import { mapState, mapActions } from 'vuex'

export default {
  data() {
    return {
      msg: ''
    }
  },
  props: ['clientid'],
  computed: {
    ...mapState({
      messages: state => state.messages
    })
  },
  methods: {
    trySendMessage() {
      this.newMessage({
        text: this.msg,
        sender: this.clientid
      })
      this.resetMessage()
    },
    resetMessage() {
      this.msg = ''
    },
    ...mapActions(['newMessage'])
  }
}
</script>
// 使用mapState来生成对共享消息集合的引用。
// 使用mapActions来生成创建一个新消息的动作（action）。
```

### 参考

* [[译] VUE 和 VUEX 中的数据流](https://juejin.im/entry/58007bcf0bd1d00058eefe69?utm_source=gold-miner&utm_medium=readme&utm_campaign=github)


