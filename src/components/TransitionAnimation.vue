<template>
<div>
  <button @click="isShow = true">Enter</button>
  <button @click="isShow = false">Leave</button>
  <button @click="isShow = !isShow">Toggle</button>

  <transition name="bounce">
    <p v-if="isShow">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris facilisis enim libero, at lacinia diam fermentum id. Pellentesque habitant morbi tristique senectus et netus.
    </p>
  </transition>
</div>
</template>

<script>

export default {
  name: 'TransitionAnimation',
  data() {
    return {
      isShow: true
    }
  }
}
</script>

<style lang="scss" scoped>

.bounce-enter-active {
  animation: bounce-in 1s;
}
.bounce-leave-active {
  animation: bounce-in 1s reverse;
}

@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(2);
  }
  100% {
    transform: scale(1);
  }
}

</style>
