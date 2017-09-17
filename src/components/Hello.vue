<template>
  <div class="hello">
    <section class="section">
      <div class="container">
        <h1 class="title  is-4">
          Привет, {{ user.name }}
        </h1>
        <br>
        <p class="subtitle">

          <h1 class="title is-2">
            У тебя <b>100 <span class="icon is-small"><i class="fa fa-tree"></i></span></b>
          </h1>
          <br>
          <router-link class="button is-large" v-bind:to="'/bonuses'"> Потратить</router-link>
        </p>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      user: {
        name: "Лиза"
      }
    }
  }
}
</script>


<style scoped>

</style>
