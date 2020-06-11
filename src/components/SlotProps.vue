<template>
<div>
  <slot :item="{ name: 'item-name', price: 100 }"></slot>
</div>
</template>

<script>


export default {
  name: 'SlotProps',
}
</script>

<style lang="scss">

</style>
