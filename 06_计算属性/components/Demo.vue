<template>
  <div class="hello">
    {{msg}}
    <button @click="fn">点击</button>
  </div>
</template>

<script>
export default {
  name: 'Demo',
  props: ['msg'],
  setup(props,context) {
    const fn = () => {
      context.emit("hello",'张三')
    }

    return {
      fn
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
