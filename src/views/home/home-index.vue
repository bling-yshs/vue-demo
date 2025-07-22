<template>
  <div>
    <Input></Input>
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
  console.log(obj.value)
  console.log(await (await fetch('https://xiaohai.ystech.top/test')).json())
}
</script>
