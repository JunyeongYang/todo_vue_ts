<template>
  <div>
    <Dropdown />
    <Accordion />
  </div>
</template>

<script lang="ts">
  import {Vue, Component} from 'vue-property-decorator'
  import Dropdown from '@/components/toggle/Dropdown.vue'
  import Accordion from '@/components/toggle/Accordion.vue'

  @Component({
    components: {
      Dropdown,
      Accordion,
    },
  })
  export default class Toggle extends Vue {

  }
</script>

<style>

</style>