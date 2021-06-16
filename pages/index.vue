<template>
  <div
    class="container"
    :style="{
      width: pageData.width + 'px',
      height: pageData.height + 'px',
      backgroundColor: pageData.backgroundColor,
    }"
  >
    <component
      v-for="component in pageData.components"
      :key="component.id"
      :is="component.componentID"
      :style="{
        width: `${component.config.style.size.width}px`,
        height: `${component.config.style.size.height}px`,
        top: `${component.config.style.position.y}px`,
        left: `${component.config.style.position.x}px`,
      }"
      >hi</component
    >
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import AntD from 'ant-design-vue'

Vue.use(AntD)

export default Vue.extend({
  data() {
    return {
      pageData: {
        name: '',
        width: 1920,
        height: 1080,
        backgroundColor: 'red',
        components: [
          {
            id: 121,
            componentID: 'a-button',
            config: {
              style: {
                size: { width: 100, heigth: 200 },
                position: { x: 300, y: 400 },
              },
            },
          },
        ],
      },
      AntD,
    }
  },
  async fetch() {
    // password 111111
    // this.pageData = await this.$axios
    //   .$get('http://www.mockhttp.cn/mock/page_data')
    //   .then((res) => res)
  },
})
</script>

<style>
.container {
  padding: 0;
  margin: 0;
  position: relative;
}

.container > * {
  position: absolute;
}
</style>
