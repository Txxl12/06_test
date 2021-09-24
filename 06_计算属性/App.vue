<template>
  姓 <input type="text" v-model="state.firstName">
  名 <input type="text" v-model="state.lastName">
  姓名 <input type="text" v-model="state.fullName">
</template>

<script>
import { reactive, computed } from 'vue'

export default {
  name: 'App',
  setup() {
   let state = reactive({
     firstName: '张',
     lastName: '三',
     fullName: computed({
       get() {
         return state.firstName + '-' + state.lastName
       },
       set(val) {
         state.firstName = val.split('-')[0]
         state.lastName = val.split('-')[1]
       }
     })
   })
   return {
     state
   }
  }
}
</script>

