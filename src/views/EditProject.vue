<template>
  <h1>Edit Project {{ id }}</h1>
  <div v-if="project">
    <form @submit.prevent="handleSubmit">
      <label>Title:</label>
      <input type="text" v-model="project.title" required />
      <label>Details:</label>
      <textarea
        v-model="project.details"
        cols="30"
        rows="10"
        required
      ></textarea>
      <button>Edit Project</button>
    </form>
  </div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      uri: "http://localhost:3000/projects/" + this.id,
      project: null,
    };
  },
  mounted() {
    fetch(this.uri)
      .then((res) => res.json())
      .then((data) => (this.project = data))
      .catch((err) => console.log(err.message));
  },
  methods: {
    handleSubmit() {
      // fetch a PATCH method to update project
      fetch(this.uri, {
        method: "PATCH",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(this.project),
      })
        .then(this.$router.push("/"))
        .catch((err) => console.log(err.message));
    },
  },
};
</script>

<style>
</style>