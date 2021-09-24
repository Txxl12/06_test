<template>
  <Demo msg="2122" @hello="sayHello"></Demo>
</template>

<script>
import Demo from './components/Demo.vue'
export default {
  name: 'App',
  components: {
    Demo
  },
  setup() {
    const sayHello = (value) => {
      console.log(`你好,我是${value}`);
    }
    return {
      sayHello
    }
  }
}
</script>

