<template>
  <div class="row">
    <!-- <div v-for="column in list" :key="column.id" class="col-4">
      <img :src="column.avatar" :alt="column.title">
      <h5>{{column.title}}</h5>
      <p>{{column.description}}</p>
      <a href="#">进入专栏</a>
    </div> -->
    <div v-for="column in ColumnList" :key="column.id" class="col-4 mb-4">
      <div class="card h-100 shadow-sm">
        <div class="card-body text-center">
          <img :src="column.avatar" :alt="column.title" class="rounded-circle shadow-sm border w-25 border-light my-3" >
          <h5 class="card-title">{{column.title}}</h5>
          <p class="card-text text-left" style="text-align: left">{{column.description}}</p>
          <a href="#" class="btn btn-outline-primary">进入专栏</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from 'vue'
export interface ColumnProps {
  id: number;
  title: string;
  description: string;
  avatar?: string;
}

export default defineComponent({
  name: 'ColumnList',
  props: {
    list: {
      type: Array as PropType<ColumnProps[]>,
      requireed: true
    }
  },
  setup (props) {
    const ColumnList = computed(() => {
      return props.list?.map(column => {
        if (!column.avatar) {
          column.avatar = 'https://images.dog.ceo/breeds/rottweiler/n02106550_8146.jpg'
        }
        return column
      })
    })
    return {
      ColumnList
    }
  }
})
</script>
