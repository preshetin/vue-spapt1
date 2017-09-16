<template>

  <!-- Hero content: will be in the middle -->

    <div class="container has-text-centered is-default">
      <h1 class="title">
        UniCoinddd
      </h1>
      <ul>
        <li v-for="project in projects">
          {{ project.slug }}
        </li>
      </ul>
    </div>


</template>

<script>
export default {
  name: 'projects',
  mounted() {
    console.log('Projecsddddsssts mounted!');
    axios.get("https://api.whizzmate.com/services/plans")
      .then(response => {this.projects = response.data})
  },

  data() {
    return {
      projects: ['one', 'two']
    }
  }
}
</script>
<!-- styling for the component -->
<style>
#projects {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
