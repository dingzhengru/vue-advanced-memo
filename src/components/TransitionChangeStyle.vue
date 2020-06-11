<template>
<div>
  <button @click="style['font-size'] = '2rem'">Enter</button>
  <button @click="style['font-size'] = '1rem'">Leave</button>

  <p class="test" :style="style">style: {{ style }}</p>

  <transition name="fade">
    <p :style="style">style: {{ style }}</p>
  </transition>
</div>
</template>

<script>

export default {
  name: 'TransitionChangeStyle',
  data() {
    return {
      style: { 'font-size': '1rem' }
    }
  }
}
</script>

<style lang="scss" scoped>

.test {
  transition: font-size 5s;
}

.fade-enter-active, .fade-leave-active {
  transition: font-size 5s;
}

.fade-enter {
  font-size: 1rem;
}

.fade-enter-to {
  font-size: 2rem;
}

.fade-leave{
  font-size: 2rem;
}

.fade-leave-to {
  font-size: 1rem;
}

</style>
