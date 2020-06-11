<template>
<div>

  <header>
    <slot name="header">
      header 預設內容
    </slot>
  </header>

  <main>
    <!-- 等同於 <slot name="default"></slot> -->
    <slot></slot>
  </main>
</div>
</template>

<script>

export default {
  name: 'SlotBasic',
}
</script>

<style lang="scss">

</style>
