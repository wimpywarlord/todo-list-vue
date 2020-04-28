<template>
  <div class="container">
    <ul>
      <div class="row" style="  border: 2px solid black;" v-for="todo in tasks" :key="todo.id">
        <div class="col-2 center">
          <input
            @click="$emit('completed_stat',todo.id)"
            v-if="todo.completed==false"
            type="checkbox"
          />
        </div>
        <div class="col-8">
          <li class="task_box">
            <h3 v-if="todo.completed==false">{{todo.task}}</h3>
            <h3 v-if="todo.completed==true" style="text-decoration: line-through;">{{todo.task}}</h3>
          </li>
        </div>
        <div class="col-2 center">
          <span id="delete_item" @click="$emit('delStat',todo.id)">X</span>
        </div>
      </div>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["tasks"]
};
</script>
<style  scoped>

li {
  list-style: none;
}
.center {
  display: flex;
  align-items: center;
  justify-content: center;
}

#delete_item {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 1.5rem;
  height: 1.5rem;
  font-weight: 800;
  background-color: #ed4c67;
  cursor: pointer;
}
</style>