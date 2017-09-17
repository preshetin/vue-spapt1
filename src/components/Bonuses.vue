<template>
  <div class="sponsors">
    <section class="section">
      <div class="container">
        <h1 class="title">
          Призы
        </h1>
        <p class="subtitle">
          Вололонтеры заработанные бонусы тратят на <strong>призы</strong>
        </p>

        <article class="message" v-bind:style="{ backgroundImage: 'url(static/bonuses/' + bonus.image + ')' }" style="width: 40%; display: inline-block; margin: 10px 10px; background-size:     cover;  background-repeat:   no-repeat; background-position: center center;  " v-for="bonus in bonuses">
          <div class="message-body" style="color:white; font-weight:700; text-shadow: 1px 1px #000000;">
            <br><br><br><br><br><br>
            {{ bonus.title }}
            <br>
              {{ bonus.price }} &nbsp; <span class="icon is-small"><i class="fa fa-tree"></i></span>

          </div>
        </article>

      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'sponsors',
  data () {
    return {
      bonuses: [
        {
          title: "8 часов Имагуру",
          description: "some desc",
          image: "imaguru.jpg",
          price: 30,
        },
        {
          title: "OZ.by",
          description: "Книга на выбор",
          image: "oz.jpg",
          price: 20
        },
        {
          title: "Фотолаборатория",
          description: "some desc",
          image: "prizrakakvest.jpg",
          price: 40,
        },
        {
          title: "Silverscreen",
          description: "some desc",
          image: "silverscreen.jpg",
          price: 10,
        }
      ],
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>


<style scoped>

</style>
