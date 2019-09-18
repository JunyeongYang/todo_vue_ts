<template>
  <div class="dropdown">
    <span>{{ text }}</span>
    <button class="btn btn-secondary dropdown-toggle" @click="toggle" type="button" id="dropdownMenuButton"
      data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      Dropdown button
    </button>
    <div class="dropdown-menu show" v-show="show" aria-labelledby="dropdownMenuButton">
      <a class="dropdown-item" href="#">Action</a>
      <a class="dropdown-item" href="#">Another action</a>
      <a class="dropdown-item" href="#">Something else here</a>
    </div>
  </div>
</template>

<script lang="ts">
  import {Vue, Component, Mixins} from 'vue-property-decorator'
  import Toggle from './Index.vue'
  import eventBus from '@/common/event-bus.ts'

  @Component({
    components: {
      Toggle,
    }
  })
  export default class Dropdown extends Mixins(Toggle){
    private text: string = ''
    created() {
      eventBus.$on('sendText', (text: string) => this.text = text)
    }
  }
</script>

<style>
  .dropdown {
    width: 500px;
  }
</style>