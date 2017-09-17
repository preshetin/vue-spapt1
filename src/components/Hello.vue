<template>
  <div class="hello">
    <section class="section">
      <div class="container">
        <h1 class="title">
          Привет, {{ user.name }}
        </h1>
        <p class="subtitle">
          У тебя <b>100 <span class="icon is-small"><i class="fa fa-tree"></i></span></b>
          <br>
          <router-link v-bind:to="'/bonuses'"> Потратить</router-link>
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
