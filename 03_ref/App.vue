<template>
  <h1>APP组件</h1>
  <div>姓名:{{name}}</div>
  <div>年龄:{{age}}</div>
  <button @click="updataInfo">修改个人信息</button>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'App',
  setup() {
    let name = ref('张三')
    let age = ref(18)
    const updataInfo = () => {
      name.value = "李四"
      age.value = 20
      console.log(name,age);
    }

    return {
      name,
      age,
      updataInfo
    }
  }
}
</script>

