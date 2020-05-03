<!--
 * @Author: Bamboo
 * @AuthorEmail: bamboo8493@126.com
 * @AuthorDescription:
 * @Modifier:
 * @ModifierEmail:
 * @ModifierDescription:
 * @Date: 2020-05-03 20:17:38
 * @LastEditTime: 2020-05-03 20:35:26
-->
<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <tree :data="treeData"></tree>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import Tree from '@/components/recursion/Tree.vue'

@Component({
  components: {
    Tree
  }
})
export default class HelloWorld extends Vue {
  @Prop() private msg!: string

  treeData: [object] = [
    {
      title: 'Web全栈架构师',
      children: [
        {
          title: 'Java架构师'
        },
        {
          title: 'JS高级',
          children: [
            {
              title: 'ES6'
            },
            {
              title: '动效'
            }
          ]
        },
        {
          title: 'Web全栈',
          children: [
            {
              title: 'Vue训练营',
              expand: true,
              children: [
                {
                  title: '组件化'
                },
                {
                  title: '源码'
                },
                {
                  title: 'docker部署'
                }
              ]
            },
            {
              title: 'React',
              children: [
                {
                  title: 'JSX'
                },
                {
                  title: '虚拟DOM'
                }
              ]
            },
            {
              title: 'Node'
            }
          ]
        }
      ]
    }
  ]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
