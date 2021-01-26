<template>
  <div v-if="job">
    <h1>{{ job.title }}</h1>
    <p>The job id is {{job.id}}</p>
    <p>{{ job.details}}</p>
  </div>
  <div v-else>
    <br><br><br>
    Loading job details....
  </div>
</template>

<script>
export default {
  name: "jobDetails",
  props: ['id'],
  //data(){
  //  return{
  //    id: this.$route.params.id
  //  }
  //},
  data(){
    return {
      job: null
    }
  },
  mounted(){
    fetch('http://localhost:3000/jobs/' + this.id)
      .then(res => res.json())
      .then(data => this.job = data)
      .catch(err =>console.log(err.message))
  }
}
</script>

<style scoped>

</style>