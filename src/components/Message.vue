<template>
  <div>
    <input type="text" v-model="message">
    <div>{{ message }}</div>
    <button @click="addCount">숫자를 증가시킵니다.</button>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop, Emit } from 'vue-property-decorator'

@Component
export default class Message extends Vue {
  // public message: string = '메세지를 입력해주세요'
  @Prop() public message!: string

  count = 0

  @Emit()
  addCount() {
    this.count++
  }
}
</script>

<style>

</style>