<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/> -->
  <div class="container">
    <column-list :list="list"></column-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
// import HelloWorld from './components/HelloWorld.vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import ColumnList, { ColumnProps } from '@/components/ColumnList.vue'

const testData: ColumnProps[] = [
  {
    id: 1,
    title: 'test1的专栏',
    description: 'test1的专栏的描述，有一段很有意思的内容，啦啦啦',
    avatar: 'https://images.dog.ceo/breeds/germanshepherd/n02106662_7238.jpg'
  },
  {
    id: 2,
    title: 'test2的专栏',
    description: 'test1的专栏的描述，有一段很有意思的内容，啦啦啦啦啦啦啦啦啦啦啦啦啦啦啦'
    // avatar: 'https://images.dog.ceo/breeds/germanshepherd/n02106662_7238.jpg'
  },
  {
    id: 3,
    title: 'test3的专栏',
    description: 'test1的专栏的描述，有一段很有意思的内容，啦啦啦',
    avatar: 'https://images.dog.ceo/breeds/germanshepherd/n02106662_7238.jpg'
  },
  {
    id: 4,
    title: 'test4的专栏',
    description: 'test1的专栏的描述，有一段很有意思的内容，啦啦啦',
    avatar: 'https://images.dog.ceo/breeds/germanshepherd/n02106662_7238.jpg'
  }
]

export default defineComponent({
  name: 'App',
  components: {
    // HelloWorld,
    ColumnList
  },
  setup () {
    return {
      list: testData
    }
  }
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
