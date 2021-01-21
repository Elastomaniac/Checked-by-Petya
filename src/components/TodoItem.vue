<template>
  <li>
    <span v-bind:class="{ done: todo.complited }">
      <input type="checkbox" />
      <strong>{{ todo.id }}</strong>
      {{ todo.title }}
    </span>
    <button class="rm">&times;</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
li {
  border: 1px solid#ccc;
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 2rem;
  margin-bottom: 1rem;
}
.rm {
  backgrounf: red;
  color: #fff;
  border-radius: 50%;
  font-weight: bold;
}
input {
  margin-right: 1rem;
}
.done {
  text-decoration: line-through;
}
</style>
 