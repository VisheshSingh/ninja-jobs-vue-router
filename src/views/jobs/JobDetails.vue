<template>
  <div v-if="job">
    <h2>{{ job.title }}</h2>
    <p>Job Details - {{ id }}</p>
    <p>{{ job.details }}</p>
  </div>
  <div v-else>
    <p>Loading...</p>
  </div>
</template>

<script>
export default {
  name: 'JobDetails',
  props: ['id'],
  data() {
    return {
      job: null,
    };
  },
  mounted() {
    fetch(`http://localhost:3000/jobs/${this.id}`)
      .then((res) => res.json())
      .then((data) => (this.job = data))
      .catch((err) => console.error(err));
  },
};
</script>

<style></style>
