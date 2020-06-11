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

<style lang="scss">

.fade-enter-active, .fade-leave-active {
  transition: all 1s;
}

.fade-enter {
  background: green;
}

.fade-enter-to {
  background: blue;
}

.fade-leave{
  background: orange;
}

.fade-leave-to {
  background: red;
}

</style>
