<template>
  <h1>All Jobs</h1>
  <div v-for="job in jobs" :key="job.id">
    <router-link :to="{ name: 'JobDetails', params: { id: job.id } }"
      ><h3>{{ job.title }}</h3></router-link
    >
  </div>
</template>

<script>
export default {
  name: 'Jobs',
  data() {
    return {
      jobs: [],
    };
  },
  mounted() {
    fetch('http://localhost:3000/jobs')
      .then((res) => res.json())
      .then((data) => (this.jobs = data))
      .catch((err) => console.error(err));
  },
};
</script>

<style>
h3 {
  background-color: #ccc;
  padding: 20px 10px;
  border-radius: 8px;
  cursor: pointer;
}

h3:hover {
  background: #eee;
}

a {
  text-decoration: none;
  color: #2c3e50;
}
</style>
