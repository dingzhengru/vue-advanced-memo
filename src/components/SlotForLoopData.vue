<template>
<div>
  <div v-for="(item, index) in items" :key="index">
    <slot :item="item">
      {{ item }}
    </slot>
  </div>
</div>
</template>

<script>


export default {
  name: 'SlotForLoopData',
  props: {
    items: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style lang="scss">

</style>
