<!--
 * @Author: Bamboo
 * @AuthorEmail: bamboo8493@126.com
 * @AuthorDescription:
 * @Modifier:
 * @ModifierEmail:
 * @ModifierDescription:
 * @Date: 2020-05-03 18:50:26
 * @LastEditTime: 2020-05-03 19:27:40
-->
<template>
  <div class="tree-node">
    <div @click="toggle" :style="{ paddingLeft: level - 1 + 'em' }">
      <label>{{ model.title }}</label>
      <span v-if="isFolder">[{{ open ? "-" : "+" }}]</span>
    </div>
    <div v-show="open" v-if="isFolder">
      <tree-node class="item" v-for="model in model.children"
        :model="model" :key="model.title"
        :level="level + 1"></tree-node>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class TreeNode extends Vue {
  @Prop({
    type: Object,
    required: true
  }) private model!: any

  @Prop({
    type: Number,
    default: 1
  }) private level!: number

  open:Boolean = false

  get isFolder() {
    return this.model.children && this.model.children.length
  }

  toggle() {
    if (this.isFolder) {
      this.open = !this.open
    }
  }
}
</script>

<style lang="sass" scoped></style>
