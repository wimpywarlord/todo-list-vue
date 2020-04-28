<template>
  <div class="row mb-3 mt-3">
    <div class="col-12 center">
      <input
        type="email"
        class="form-control"
        placeholder="Enter a task here"
        style="border: 2px solid red; width:40vh;"
        id="exampleInputEmail1"
        v-model="yummy"
        aria-describedby="emailHelp"
      />
      <button @click="$emit('taskEntered',yummy)" type="button" class="btn btn-danger ml-1">Add</button>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      yummy: ""
    };
  }
};
</script>
<style scoped>
.center {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>