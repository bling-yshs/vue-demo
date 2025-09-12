<template>
  <div>
    <div class="text-orange-500">hello world</div>
    <Button class="active:scale-95" @click="hi">这是一个测试按钮哦~</Button>
    <Input v-model="inp"></Input>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const inp = ref('')

import { Button } from '@/components/ui/button'
import { Input } from '@/components/ui/input'

async function hi() {
  console.log('ok')
}
</script>
