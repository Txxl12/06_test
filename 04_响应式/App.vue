<template>
  <h1>APP组件</h1>
  <div>姓名:{{person.name}}</div>
  <div>年龄:{{person.age}}</div>
  <div>职业:{{person.job.type}}</div>
  <div>薪资:{{person.job.salary}}</div>
  <div>爱好:{{person.hoppy}}</div>
  <div>{{person.job.a.b.c}}</div>
  <button @click="updataInfo">修改个人信息</button>
</template>

<script>
import { reactive } from 'vue'
export default {
  name: 'App',
  setup() {
    let person = reactive({
      name: '张三',
      age: 12,
      job: {
        type: '前端',
        salary: '30',
        a: {
          b: {
            c: '666'
          }
        }
      },
      hoppy: ['1', '2', '3']
    })

    const updataInfo = () => {
      person.name = '李四'
      person.age = 18
      person.job.type = 'UI'
      person.job.salary = '60'
      person.job.a.b.c = '999'
      person.hoppy[0] = '4'
    }

    return {
      person,
      updataInfo
    }
  }
}
</script>

