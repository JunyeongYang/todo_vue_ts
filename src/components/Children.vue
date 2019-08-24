<template>
  <div>
    <p>
      {{ alertMessage }}
    </p>
    {{ childrenMessage }}
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop, Watch } from 'vue-property-decorator'

@Component
export default class Children extends Vue {
  public alertMessage: string = ''
  @Prop() private childrenMessage?: string

  @Watch('childrenMessage')
  public update() {
    this.alertMessage = '변경'
  }
}
</script>

<style>

</style>