<!--
 * @Author: Bamboo
 * @AuthorEmail: bamboo8493@126.com
 * @AuthorDescription:
 * @Modifier:
 * @ModifierEmail:
 * @ModifierDescription:
 * @Date: 2020-05-03 19:17:30
 * @LastEditTime: 2020-05-03 20:34:51
~-->
<template>
  <div class="tree">
    <tree-node v-for="item in data" :key="item.title" :model="item"></tree-node>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import TreeNode from '@/components/recursion/TreeNode.vue'

@Component({
  components: {
    TreeNode
  }
})
export default class Tree extends Vue {
  @Prop({
    type: Array,
    required: true
  })
  private data!: [object]
}
</script>

<style scoped>
.tree {
  text-align: left;
}
</style>
