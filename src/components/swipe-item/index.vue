<template>
  <div class="vc-swipe-item" v-swipe:vertical="{}">
    <slot></slot>
  </div>
</template>

<script>
  import { swipeDirective } from '../../mixins/event/swipe.js'

  export default {
    name: 'vc-swipe-item',

    props: {
      onEnter: {
        type: Function,
        default: null
      },
      onLeave: {
        type: Function,
        default: null
      },
    },

    mounted () {
      this.$parent && this.$parent.swipeItemCreated();
    },

    destroyed () {
      this.$parent && this.$parent.swipeItemDestroyed()
    },

    directives: {
      swipe: swipeDirective
    }
  }
</script>

<style scoped lang="scss">
</style>
