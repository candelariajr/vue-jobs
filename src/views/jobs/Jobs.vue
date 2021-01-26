<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" :key="job.id">
    <router-link :to="{name : 'jobDetails', params: { id: job.id}}">
      <h2>{{job.title}}</h2>
    </router-link>
  </div>
</template>

<script>
  export default {
    name: "Jobs",
    data(){
      return {
        jobs:[
          {title: "Job1", id: 1, details: "Lorem"},
          {title: "Job2", id: 2, details: "Lorem2"},
          {title: "Job3", id: 3, details: "Lorem3"}
        ]
      }
    }
  }
</script>

<style scoped>

</style>