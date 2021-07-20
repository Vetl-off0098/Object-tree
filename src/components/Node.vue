<template>
  <div class="wrap">
    <div class="obj">
      {{ content }}
    </div>
    <div class="readyMultiply" v-if="hasKeyInObject" @click="isOpenKey = !isOpenKey">
      <span v-if="!isOpenKey">+</span>
      <span v-else>-</span>
    </div>
    <div class="child" v-if="isOpenKey">
      <Node
        v-for="key in obj"
        :key="key + obj.key"
        :obj="key"/>
    </div>
  </div>
</template>

<script>
import Node from '@/components/Node.vue'

export default {
  name: 'Node',
  props: ['obj'],
  components: {
    Node
  },
  computed: {
    hasKeyInObject () {
      return (typeof this.obj === 'object') && Object.entries(this.obj).length > 0
    },
    content () {
      if (typeof this.obj === 'object') {
        return 'Object'
      } else {
        return this.obj
      }
    }
  },
  data () {
    return {
      isOpenKey: false
    }
  }
}
</script>

<style scoped lang="scss">
.wrap {
  display: flex;
}
.obj {
  width: 120px;
  height: 80px;
  border: 2px solid purple;
  display: flex;
  justify-content: center;
  align-items: center;
}
.readyMultiply {
  cursor: pointer;
  width: 30px;
  height: 30px;
  border: 2px solid red;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
