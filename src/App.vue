<template>

  <div>{{sum}}</div>
  <button @click="sum++">+1</button>
  <hr>

  <div>{{msg}}</div>
  <button @click="msg+='!'">更新</button>
  <hr>

  <div>{{person.name}}</div>
  <div>{{person.age}}</div>
  <button @click="person.name+='~'">修改姓名</button>
  <button @click="person.age++">修改年龄</button>
</template>

<script>
import { reactive, ref, watch } from 'vue'

export default {
  name: 'App',
  // watch: {
  //   sum: {
  //     deep: true,
  //     immediate: true,
  //     handler(newVal, oldVal) {
  //       console.log(newVal, oldVal);
  //     }
  //   }
  // },
  setup() {

    let sum = ref(0)
    let msg = ref('你好')
    let person = reactive({
      name: '张三',
      age: 19
    })

    // watch(监视对象,监视回调,监视配置)

    // 1、监视ref定义的一个响应式数据
    /* watch(sum,(newVal, oldVal) => {
      console.log(newVal, oldVal);
    }) */

    // 2、监视ref定义的多个响应式数据
    /* watch([sum, msg], (newVal, oldVal) => {
      console.log(newVal, oldVal);
    }, { immediate: true }) */

    /* 3、监视reactive定义的响应式数据的全部属性
          无法正确获取oldVal
          强制开启深度监视(deep配置无效)
    */
    /* watch(person, (newVal, oldVal) => {
      console.log(newVal, oldVal);
    }) */

    /* 4、监视reactive定义的响应式数据的某个属性
          无法正确获取oldVal
          强制开启深度监视(deep配置无效)
    */
    /* watch(() => person.name, (newVal, oldVal) => {
      console.log(newVal, oldVal);
    }) */

    /* 5、监视reactive定义的响应式数据的某些属性
          无法正确获取oldVal
          强制开启深度监视(deep配置无效)
    */
    /* watch([() => person.name, () => person.age], (newVal, oldVal) => {
      console.log(newVal, oldVal);
    }) */


    return {
      sum,
      msg,
      person
    }
  }
}
</script>

