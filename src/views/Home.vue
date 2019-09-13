<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/> -->
    <Message message="프롭스"/>
    <Children @counter="counter" />
    <p>{{ count }}</p>
    <button @click="changeMessage">Change Message</button>
    {{count}}
    <MyCheckbox v-model="checked" @changed="change" />
    {{text}}
  </div>
</template>

<script lang="ts">
import { Component, Vue, Provide } from 'vue-property-decorator'
import HelloWorld from '@/components/HelloWorld.vue' // @ is an alias to /src
import Message from '@/components/Message.vue'
import Children from '@/components/Children.vue'
import MyCheckbox from '@/components/MyCheckbox.vue'

@Component({
  components: {
    HelloWorld,
    Message,
    Children,
    MyCheckbox,
  },
})
export default class Home extends Vue {
  private message: string = 'hello world'
  private count: number = 0
  private checked: boolean = false
  private text: string = '동의하지 않습니다.'

  @Provide('message') private msg: string = 'Provide/Injdex example'

  private changeMessage() {
    this.message = 'changed Message'
  }

  private counter() {
    this.count++
  }

  private change(checked: boolean) {
    this.checked = checked
    this.text = checked ? '동의합니다.' : '동의하지않습니다.'
  }


}
</script>
