<template>
<div>
    <p>
        {{testData}}
        <span :title="message" v-if="seen">鼠标悬停几秒钟查看此处动态绑定的提示信息！</span>
        
    </p>
    <ol style="margin-left:50px">
    <li v-for="todo in todos" :key="todo.text">
      {{ todo.text }}
    </li>
  </ol>
  <button v-on:click="reverseMessage">逆转消息</button>
  <input v-model="testData">
</div>
</template>

<script>

export default {
  data() {
    return {
      testData: "hello",
      message:'页面加载于 ' + new Date().toLocaleString(),
      seen:false,
         todos: [
      { text: 'test1' },
      { text: 'test2' },
      { text: 'test3' }
    ]
    };
  },
  computed : {
  },
  components: {
  },
  methods: {
    reverseMessage: function () {
      this.testData = this.testData.split('').reverse().join('')
    }
  }
};
</script>
