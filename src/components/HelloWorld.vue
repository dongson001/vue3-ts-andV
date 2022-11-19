<template>
  <div class="draggable-box">
    <div class="left-box">
      <nested-draggable :tasks="state.list1" />
    </div>
    <div class="btn-box">
      <a-button>添加</a-button>
    </div>
    <div class="right-box">
      <nested-draggable :tasks="state.list2" />
    </div>
  </div>
</template>
<script setup>
import { ref, watch } from 'vue';
import nestedDraggable from './nested.vue';
let state = ref({
  list1: [
    {
      name: 'task 1',
      tasks: [
        {
          name: 'task 2',
          tasks: [],
        },
      ],
    },
    {
      name: 'task 3',
      tasks: [
        {
          name: 'task 4',
          tasks: [],
        },
      ],
    },
    {
      name: 'task 5',
      tasks: [],
    },
  ],
  list2: [
    {
      name: 'task 19',
      tasks: [
        {
          name: 'task 29',
          tasks: [],
        },
      ],
    },
    {
      name: 'task 39',
      tasks: [
        {
          name: 'task 47',
          tasks: [],
        },
      ],
    },
    {
      name: 'task 59',
      tasks: [],
    },
  ],
});
</script>
<style scoped>
.draggable-box {
  display: flex;
  width: 1000px;
}
.btn-box {
  width: 100px;
  margin: 0 10px;
}
.left-box {
  flex: 1;
  border: 1px solid #ccc;
}
.right-box {
  flex: 1;
  border: 1px solid #ccc;
}
</style>
