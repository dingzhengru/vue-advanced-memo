<template>
<div id="app">
  <h1>Vue Advanced Memo</h1>
  <hr />

  <h2>Slot</h2>
  <h3>SlotBasic</h3>
  <SlotBasic>
    <template v-slot:default>
      slot:default content
    </template>
  </SlotBasic>
  
  <h3>SlotProps</h3>
  <SlotProps>
    <template v-slot:default="itemProps">
      {{ itemProps.item.name }}
    </template>
  </SlotProps>

  <!-- 也可以用 js 接收 Object 的方式，直接 { props } -->
  <SlotProps>
    <template v-slot:default="{ item }">
      {{ item.price }}
    </template>
  </SlotProps>

  <h3>SlotForLoopData</h3>
  <span>也可以插入 Compoent 中的 for loop 內容中</span>
  <SlotForLoopData :items="items">
    <template v-slot:default="{ item }">
      {{ item.name }} {{ item.price }}
    </template>
  </SlotForLoopData>

  <hr />
  <h2>Transition</h2>
  <p>此標籤是專門用來處理 "vue 事件"切換狀態時的轉變動畫，ex: v-if, v-show, vue-router 的切換頁面</p>
  <h3>TransitionBasic</h3>
  <TransitionBasic />

  <h3>TransitionAnimation</h3>
  <TransitionAnimation />
</div>
</template>

<script>
import SlotBasic from '@/components/SlotBasic'
import SlotProps from '@/components/SlotProps'
import SlotForLoopData from '@/components/SlotForLoopData'

import TransitionBasic from '@/components/TransitionBasic'
import TransitionAnimation from '@/components/TransitionAnimation'

export default {
  name: 'App',
  components: {
    SlotBasic,
    SlotProps,
    SlotForLoopData,
    TransitionBasic,
    TransitionAnimation
  },
  data() {
    return {
      items: [
        {
          name: 'item-1',
          price: 1000
        },
        {
          name: 'item-2',
          price: 2000
        },
        {
          name: 'item-3',
          price: 3000
        },
        {
          name: 'item-4',
          price: 4000
        },
        {
          name: 'item-5',
          price: 5000
        },
      ]
    }
  }
}
</script>

<style lang="scss">

</style>
