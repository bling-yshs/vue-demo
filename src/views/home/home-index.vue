<template>
  <div>
    <div class="text-orange-500">hello world</div>
    <Button class="active:scale-95" @click="hi">这是一个测试按钮哦~</Button>
    <Input v-model="obj.name"></Input>
    <div>{{ obj.name }}</div>
  </div>
</template>

<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { Input } from '@/components/ui/input'
import { ref } from 'vue'

interface Obj {
  id: string
  name: string
}

const obj = ref<Obj>({ id: '', name: '' })

async function hi() {
  let response = await fetch('\n' +
    'https://api.vc.bilibili.com/link_setting/v1/link_setting/get?build=0&mobi_app=web&msg_notify=1&show_unfollowed_msg=1&web_location=333.1007')
  console.log((await response.text()))
}
</script>
