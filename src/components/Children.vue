<template>
  <div>
    <button @click="counter">숫자를 증가시킵니다.</button>
    {{ message }}
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop, Watch, Emit, Inject } from 'vue-property-decorator'

@Component
export default class Children extends Vue {
  @Inject() public readonly message!: string

  @Emit()
  private counter() {}
}
</script>

<style>

</style>