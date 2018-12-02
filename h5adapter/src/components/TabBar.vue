<template>
<div class="tab-bar">
  {{navList}}
  <nav>
    <a 
      href="javascript:;" 
      :class="{active: activeIndex == index}" 
      v-for="(item, index) in navList" 
      :key="index"
      @click="handlerChange(index, item)"
    >
      {{item[label]}}
    </a>
  </nav>
</div>
</template>
<script>
export default {
  props: {
    navList: Array,
    label: {
      type: String,
      default: 'text'
    },
    defaultIndex: Number
  },
  data () {
    return {
      activeIndex: 0
    }
  },
  watch: {
    defaultIndex (index) {
      this.setDefaultIndex(index)
    }
  },
  created () {
    this.setDefaultIndex(this.defaultIndex)
  },
  methods: {
    setDefaultIndex (index) {
      this.activeIndex = index ? index : 0
    },
    handlerChange (index, item) {
      this.activeIndex = index
      this.$emit('change', index, item)
    }
  }
}
</script>
<style lang="scss" scoped>

</style>
