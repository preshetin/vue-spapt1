<template>

  <!-- Hero content: will be in the middle -->

    <div class="container has-text-centered is-default">
      <br>
      <h1 class="title">
        Проекты
        <a class="button is-large" @click="showModal()">
          <span class="icon is-medium">
            <i class="fa fa-plus"></i>
          </span>
          <span>Добавить</span>
        </a>
      </h1>

      <ul>
        <div class="box" v-for="project in projects">
          <article class="media">
            <div class="media-left">
              <figure class="image is-64x64">
                <img src="http://bulma.io/images/placeholders/128x128.png" alt="Image">
              </figure>
            </div>
            <div class="media-content">
              <div class="content">
                <p>
                  <strong>{{ project.title }}</strong> <small>@johnsmith</small> <small>31m</small>
                  <br>
                  {{ project.description}}
                </p>
              </div>
              <nav class="level is-mobile">
                <div class="level-right">
                  <div class="level-item">
                    <span class="icon is-small"><i class="fa fa-heart"></i></span> &nbsp;{{ project.bonus}}
                  </div>
                  <a class="level-item">
                    <a class="button is-success">Откликнуться</a>&nbsp;
                  </a>
                </div>
              </nav>
            </div>
          </article>
        </div>


        <div class="modal is-active" v-if="isModalShow">
          <div class="modal-background"></div>
          <div class="modal-card">
            <header class="modal-card-head">
              <p class="modal-card-title">Добавить проект</p>
              <button class="delete" aria-label="close" @click="closeModal()"></button>
            </header>
            <section class="modal-card-body">
              <div class="field is-horizontal">
                <div class="field-label is-normal">
                  <label class="label">Название</label>
                </div>
                <div class="field-body">
                  <div class="field">
                    <p class="control is-expanded has-icons-left">
                      <input class="input" type="text" placeholder="Name">
                      <span class="icon is-small is-left">
                        <i class="fa fa-user"></i>
                      </span>
                    </p>
                  </div>
                </div>
              </div>



              <div class="field is-horizontal">
                <div class="field-label is-normal">
                  <label class="label">Категория</label>
                </div>
                <div class="field-body">
                  <div class="field is-narrow">
                    <div class="control">
                      <div class="select is-fullwidth">
                        <select>
                          <option>Строительство</option>
                          <option>Помощь пожилые люди</option>
                          <option>Детский дом</option>
                        </select>
                      </div>
                    </div>
                  </div>
                </div>
              </div>


              <div class="field is-horizontal">
                <div class="field-label is-normal">
                  <label class="label">Описание</label>
                </div>
                <div class="field-body">
                  <div class="field">
                    <div class="control">
                      <textarea class="textarea" placeholder="Explain how we can help you"></textarea>
                    </div>
                  </div>
                </div>
              </div>

            </section>
            <footer class="modal-card-foot">
              <button class="button is-success">Добавить проект</button>
              <button class="button">Отмена</button>
            </footer>
          </div>
        </div>

      </ul>
    </div>


</template>

<script>
export default {
  name: 'projects',
  mounted() {
    // axios.get("https://api.whizzmate.com/services/plans")
    //   .then(response => {this.projects = response.data})
  },

  methods: {
    showModal() {
      this.isModalShow = true;
    },
    closeModal() {
      this.isModalShow = false;
    }
  },

  data() {
    return {
      isModalShow: false,
      projects: [
        {
          title: "Волонтеры Европейских игр 2019",
          description: "с июня 2018 года начнутся собеседования с кандидатами. После удачного прохождения собеседования с февраля 2019 года будут рассылаться письма-поздравления. А так же приглашение на прохождение обучения",
          bonus: "Билет на финальную игру"
        },
        {
          title: "Временное содержание кошек (egida.by)",
          description: "Мы собираемся создать документальный фильм, в котором отразить всю действительность отлова в Беларуси: кто, как и чем отлавливает собак, что с ними происходит после отлова. Мы приглашаем присоединиться волонтеров-наблюдателей",
          bonus: "Занятие по дрессировке собаки"
        }
      ]
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
