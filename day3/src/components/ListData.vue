<template>
  <div>
    <ol v-if="listTodo.length > 0">
      <li v-for="(todo, index) in listTodo" :key="index">{{ todo }}</li>
    </ol>
  </div>
</template>

<script>
export default {
  props: {
    listTodo: {
      type: Array,
      required: true,
    },
  },
};
</script>
