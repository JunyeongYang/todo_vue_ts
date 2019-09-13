<template>
  <div>
  <button @click="counter">숫자를 증가시킵니다.</button>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop, Watch, Emit } from 'vue-property-decorator'

@Component
export default class Children extends Vue {

  @Emit() 
  counter() {
    console.log('counted')
  }
  
}
</script>

<style>

</style>