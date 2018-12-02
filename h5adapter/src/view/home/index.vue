<template>
<div class="page home-page">
  <HeaderBar />
  <div>
    <TabBar :navList="nav" @change="navChange" :defaultIndex="activeIndex"  />
  </div>
  <footer></footer>
</div>
</template>
<script>
import HeaderBar from './components/HeaderBar'
import TabBar from '@/components/TabBar'
export default {
  props: {},
  data () {
    return {
      nav: [
        {text: '多点超市'},
        {text: '全球精选'}
      ],
      activeIndex: 0
    }
  },
  components: {
    HeaderBar,
    TabBar
  },
  created () {},
  mounted () {},
  watch: {},
  computed: {},
  methods: {
    navChange (index, item) {
      console.log(index, item)
    }
  }
}
</script>
<style lang="scss" scoped>
@import '@/static/scss/_default.scss';

</style>
