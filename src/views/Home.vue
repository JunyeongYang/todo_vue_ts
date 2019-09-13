<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/> -->
    <Message message="프롭스"/>
    <Children @counter="counter" />
    <p>{{ count }}</p>
    <button @click="changeMessage">Change Message</button>
    {{count}}
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import HelloWorld from '@/components/HelloWorld.vue' // @ is an alias to /src
import Message from '@/components/Message.vue'
import Children from '@/components/Children.vue'

@Component({
  components: {
    HelloWorld,
    Message,
    Children,
  },
})
export default class Home extends Vue {
  count:number = 0

  counter() {
    this.count++
  }

  public message: string = 'hello world'

  public changeMessage() {
    this.message = 'changed Message'
  }
}
</script>
