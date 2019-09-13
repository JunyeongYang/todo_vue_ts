<template>
  <input type="checkbox" :checked="checked" @change="change">
</template>

<script lang="ts">
  import {Vue, Component, Model, Emit} from 'vue-property-decorator'

  @Component
  export default class MyCheckbox extends Vue {
    @Model('change', {type: Boolean}) private readonly checked!: boolean

    @Emit('changed')
    private change(event: Event) {
      return event.target.checked
    }
  }
</script>

<style>

</style>