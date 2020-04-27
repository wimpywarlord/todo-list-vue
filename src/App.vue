<template>
  <div>
    <HeadBar></HeadBar>
    <TaskBox></TaskBox>
  </div>
</template>

<script>
import HeadBar from "./components/nav_head";
import TaskBox from "./components/tasks";

export default {
  name: "App",
  components: {
    HeadBar,
    TaskBox
  },
  data() {
    return {
      to_do_list: [
        {
          id: "1",
          task: "THIS IS SOME TASK",
          complete: false
        },
        {
          id: "1",
          task: "THIS IS SOME TASK",
          complete: false
        },
        {
          id: "1",
          task: "THIS IS SOME TASK",
          complete: false
        }
      ]
    };
  }
};
</script>

<style>
</style>
