<template>
  <div
    class="container"
    :style="{
      width: pageData.width + 'px',
      height: pageData.height + 'px',
      backgroundColor: pageData.backgroundColor,
    }"
  >
    <component :is="button">hi</component>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import AntD from 'ant-design-vue'

Vue.use(AntD)

export default Vue.extend({
  data() {
    return {
      pageData: {},
      AntD,
      button: 'a-button',
    }
  },
  async fetch() {
    // password 111111
    this.pageData = await this.$axios
      .$get('http://www.mockhttp.cn/mock/page_data')
      .then((res) => res)
  },
})
</script>

<style>
.container {
  padding: 0;
  margin: 0;
  position: relative;
}
</style>
