<template>
<div>
  <button @click="isShow = true">Enter</button>
  <button @click="isShow = false">Leave</button>
  <button @click="isShow = !isShow">Toggle</button>

  <transition name="fade">
    <p v-if="isShow">isShow: {{ isShow }}</p>
  </transition>
</div>
</template>

<script>


export default {
  name: 'TransitionBasic',
  data() {
    return {
      isShow: true
    }
  }
}
</script>

<style lang="scss" scoped>

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}

</style>
