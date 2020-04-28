<template>
  <div>
    <HeadBar></HeadBar>
    <AddTask v-on:taskEntered="taskEntered"></AddTask>
    <TaskBox v-on:delStat="deleteTask" v-on:completed_stat="change_stat" :tasks="to_do_list"></TaskBox>
  </div>
</template>

<script>
import HeadBar from "./components/nav_head";
import TaskBox from "./components/tasks";
import AddTask from "./components/addTask";

export default {
  name: "App",
  components: {
    HeadBar,
    TaskBox,
    AddTask
  },
  data() {
    return {
      to_do_list: [
        {
          id: "1",
          task: "THIS IS SOME TASK",
          completed: true
        },
        {
          id: "2",
          task: "THIS IS SOME TASK",
          completed: false
        },
        {
          id: "3",
          task: "THIS IS SOME TASK",
          completed: false
        }
      ],
      count_of_task: 4
    };
  },
  methods: {
    change_stat: function(id) {
      console.log(id);
      this.to_do_list.forEach(currentItem => {
        if (currentItem.id == id) {
          currentItem.completed = true;
        }
      });
    },
    deleteTask: function(id) {
      this.to_do_list = this.to_do_list.filter(todo => todo.id !== id);
    },
    taskEntered: function(newtask) {
      console.log(newtask);
      let new_task_obj = {
        id: this.count_of_task + 1,
        task: newtask.toUpperCase(),
        completed: false
      };
      this.to_do_list.push(new_task_obj);
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  padding: 0px;
  margin: 0px;
}
.center {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
